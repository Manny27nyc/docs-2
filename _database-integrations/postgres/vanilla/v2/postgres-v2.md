---
title: PostgreSQL (HP) (v2)
keywords: postgresql, postgres, database integration, etl postgres, postgres etl, postgresql etl, etl
permalink: /integrations/databases/postgresql/v2
summary: "Connect and replicate data from your PostgreSQL database using Stitch's PostgreSQL integration."

microsites:
  - title: "{{ page.display_name }} to Postgres"
    url: "http://postgres.topostges.com/"

key: "postgres-integration"

# -------------------------- #
#     Integration Details    #
# -------------------------- #

name: "postgres"
display_name: "PostgreSQL"
singer: true

tap-name: "Postgres"
repo-url: "Not applicable"

hosting-type: "generic"

this-version: "2"

driver: |
  [](){:target="new"}

# -------------------------- #
#       Stitch Details       #
# -------------------------- #

certified: true

frequency: "1 hour"
tier: "Standard"
port: 5432
db-type: "postgres"

## Stitch features
api-type: "platform.hp-postgres"
override-api-type: true

versions: "9.3+; 9.4+ for binlog"
ssh: true
ssl: true

## General replication features

anchor-scheduling: true
cron-scheduling: true

extraction-logs: true
loading-reports: true

table-selection: true
column-selection: true
select-all: "sometimes"
select-all-reason: "Log-based Incremental Replication must be enabled and set as the default Replication Method to use the Select All feature."

table-level-reset: true

## Replication methods

define-replication-methods: true
set-default-replication-method: true

log-based-replication-minimum-version: "9.4"
log-based-replication-master-instance: true

log-based-replication-read-replica: false
log-based-replication-read-replica-reason: "PostgreSQL only supports logical replication on master instances."
log-based-replication-read-replica-doc-link: |
  {{ link.replication.log-based-incremental | prepend: site.baseurl | append: "#limitation-7--only-supports-master-instances-postgresql" }}

## Other Replication Methods

key-based-incremental-replication: true
full-table-replication: true

view-replication: true


# -------------------------- #
#    Supported Data Types    #
# -------------------------- #

## Some data type support & handling is specific to an integration's version.

## See _data/taps/data-types/postgres/v2.yml


# -------------------------- #
#      Feature Summary       #
# -------------------------- #

feature-summary: |
  {% assign all-postgres = site.database-integrations | where:"key","postgres-integration" %}
  {% assign postgres-overview = all-postgres | where:"content-type","database-category" | first %}

  This version (v{{ integration.this-version }}) of Stitch's {{ integration.display_name }} integration optimizes replication by utilizing Avro schemas to write and validate data, thereby reducing the amount of time spent on data extraction and preparation. Compared to previous versions of the {{ integration.display_name }} integration, this version boasts increased performance and overall reduced replication time.

  Notable improvements and changes in this version also include:

  - **Expanded data type support**. This version supports additional {{ integration.display_name }} data types. Refer to the [{{ integration.display_name }} data types documentation]({{ postgres-overview.url | prepend: site.baseurl | append: "#data-types" }}) for more info.
  - **Improved handling of `JSON`, `JSONB`, and `HSTORE` data types**. In previous versions, these data types were treated as strings. This version will send them to your destination as JSON objects, which may result in [de-nesting]({{ link.destinations.storage.nested-structures | prepend: site.baseurl }}).
  - **Improved handling of schema changes in tables using Log-based Incremental Replication.** Adding and removing columns in these tables will no longer cause extraction errors. **Note**: This limitation still applies to [version 1]({{ link.replication.log-based-incremental | append: site.baseurl | append: "#limitation--structural-changes" }}).

  **Note**: The following features aren't fully supported, but are being worked on:

  - **Arrays of `DECIMAL`, `NUMERIC`, and `TIMESTAMP(TZ)` data types**
  - **Support for some flavors of {{ integration.display_name }}**. We're in the process of testing this version of our integration with other flavors of {{ integration.display_name }}, including Amazon Aurora and Amazon RDS.

  To get a look at how this version compares to the previous version of {{ integration.display_name }}, refer to the [{{ integration.display_name }} version comparison documentation]({{ postgres-overview.url | prepend: site.baseurl | append: "#supported-features" }}).


# -------------------------- #
#      Setup Requirements    #
# -------------------------- #


notice-first-line: "**PostgreSQL as an input data source**"
notice-copy: |

  This article describes how to connect {{ integration.display_name }} **as an input data source.**

  If you want to connect a {{ integration.display_name }} instance as a **destination**, refer to the [Connecting a Self-Hosted {{ integration.display_name }} Destination guide]({{ link.destinations.setup.self-hosted-postgres | prepend: site.baseurl }}).

requirements-list:
  - item: "**The `CREATEROLE` or `SUPERUSER` privilege.** Either privilege is required to create a database user for Stitch."
  - item: |
      **If using Log-based Replication**, you'll need:

      - **A database running PostgreSQL 9.4 or greater** Earlier versions of PostgreSQL do not include logical replication functionality, which is required for Log-based Replication.
      - **The `SUPERUSER` privilege.** If using logical replication, this is required to define the appropriate server settings.
      - **To connect to the master instance.** Log-based replication will only work on master instances due to a feature gap in PostgreSQL 10. [Based on their forums](https://commitfest.postgresql.org/12/788/){:target="new"}, PostgreSQL is working on adding support for using logical replication on a read replica to a future version.
      - **To check for TOASTed tables and columns**. TOASTed tables and columns in your {{ integration.display_name }} database can cause the following issues when using Log-Based Replication:

          1. Recurring `no known snapshot` errors, or 
          2. Inaccurate data replication. 

          Refer to the [{{ integration.display_name }} documentation](https://www.postgresql.org/docs/9.5/storage-toast.html){:target="new"} for more information on what TOAST is and how to identify TOASTed tables and columns in your database.
  - item: |
      **If you're not using Log-based Replication**, you'll need:

      - **A database running PostgreSQL 9.3.x or greater.** PostgreSQL 9.3.x is the minimum version Stitch supports for PostgreSQL integrations.
      - **To verify if the database is a read replica, or follower**. While we always recommend connecting a replica over a production database, this also means you may need to verify some of its settings - specifically the `max_standby_streaming_delay` and `max_standby_archive_delay` settings - before connecting it to Stitch. We recommend setting these parameters to 8-12 hours for an initial replication job, and then decreasing them afterwards.

# -------------------------- #
#     Setup Instructions     #
# -------------------------- #

setup-steps:
  - title: "Configure database connection settings"
    anchor: "connect-settings"
    content: |
      {% include integrations/templates/configure-connection-settings.html %}

  - title: "Create a Stitch database user"
    anchor: "create-a-database-user"
    content: |
      Next, you'll create a dedicated database user for Stitch. This will ensure Stitch is visible in any logs or audits, and allow you to maintain your privilege hierarchy.

      {% include integrations/templates/create-database-user-tabs.html %}

  - title: "Configure Log-based Incremental Replication"
    anchor: "configure-log-based-incremental-replication"
    content: |
      {% include note.html type="single-line" content="**Note**: Skip this step if you're not planning to use Log-based Incremental Replication. [Click to skip ahead](#connect-stitch)." %}

      {% include integrations/databases/setup/binlog/configure-server-settings-intro.html %}

      In this section:

      {% for substep in step.substeps %}
      - [Step 3.{{ forloop.index }}: {{ substep.title | flatify }}](#{{ substep.anchor }})
      {% endfor %}
    substeps:
      - title: "Install the wal2json plugin"
        anchor: "install-wal2json-plugin"
        content: |
          To use Log-based Replication for your {{ integration.display_name }} integration, you must install the [wal2json](https://github.com/eulerto/wal2json){:target="new"} plugin. The wal2json plugin outputs JSON objects for logical decoding, which Stitch then uses to perform Log-based Replication.

          Steps for installing the plugin vary depending on your operating system. Instructions for each operating system type are in the wal2json's GitHub repository:

          - [Unix-based operating systems](https://github.com/eulerto/wal2json#unix-based-operating-systems)
          - [Windows](https://github.com/eulerto/wal2json#windows)

          After you've installed the plugin, you can move onto the next step.

      - title: "Edit the client authentication file"
        anchor: "edit-client-authentication-file"
        content: |
          Usually named `pg_hba.conf`, [this file controls how clients authenticate to the {{ integration.display_name }} database](https://www.postgresql.org/docs/9.4/static/auth-pg-hba-conf.html){:target="new"}. To ensure Stitch can read the output from the wal2json plugin, you'll need to add replication connection rules to this file. These rules translate to _"Allow the Stitch user from this IP address to perform replication on all the databases it has access to."_

          This step uses the [Stitch IP addresses for your data pipeline region]({{ link.security.ip-addresses | prepend: site.baseurl }}).

          1. Log into your {{ integration.display_name }} server as a superuser.
          2. Locate the `pg_hba.conf` file, usually stored in the database cluster's data directory. You can also locate this file by checking the value of the `hba_file` server parameter.
          3. For each Stitch IP address, add the following line to `pg_hba.conf`.

             Replace the following:

             - `<stitch_username>` with the name of the [Stitch database user](#create-a-database-user)
             - `<stitch_ip_address>` with one of the Stitch IP addresses for your data pipeline region

             {% capture code %}
             host replication <stitch_username> <stitch_ip_address> md5
             {% endcapture %}

             {% include layout/code-snippet.html code=code use-code-block=false %}

             ```conf
          {{ code | lstrip | rstrip }}
             ```

             A rule for each IP addresses for your [Stitch data pipeline region]({{ link.security.ip-addresses | prepend: site.baseurl }}) must be added to `pg_hba.conf`. As Stitch can use any one of these IP addresses to connect during the extraction process, each of them must have their own replication connection rule.

      - title: "Edit the database configuration file"
        anchor: "configure-database-parameters"
        content: |
          {% include integrations/databases/setup/binlog/vanilla-postgres.html %}

      - title: "Restart the {{ integration.display_name }} service"
        anchor: "restart-database-service"
        content: |
          After you've finished [editing the pg_hba.conf file](#edit-client-authentication-file) and [configuring the database settings](#configure-database-parameters), restart your {{ integration.display_name }} service to ensure the changes take effect.

      - title: "Create a replication slot"
        anchor: "create-replication-slot"
        content: |
          {% include integrations/databases/setup/binlog/postgres-replication-slot.html %}

  - title: "Connect Stitch"
    anchor: "connect-stitch"
    content: |
      In this step, you'll complete the setup by entering the database's connection details and defining replication settings in Stitch.

      {% for substep in step.substeps %}
      - [Step 4.{{ forloop.index }}: {{ substep.title | flatify }}](#{{ substep.anchor }})
      {% endfor %}

    substeps:
      - title: "Define the database connection details"
        anchor: "define-connection-details"
        content: |
          {% include shared/database-connection-settings.html type="general" %}

      - title: "Define the SSH connection details"
        anchor: "ssh-connection-details"
        content: |
          {% include shared/database-connection-settings.html type="ssh" %}
      
      - title: "Define the SSL connection details"
        anchor: "ssl-connection-details"
        content: |
          {% include shared/database-connection-settings.html type="ssl" %}

      - title: "Define the Log-based Replication setting"
        anchor: "define-log-based-replication-setting"
        content: |
          {% include note.html type="single-line" content="**Note**: Skip this step if you're not planning to use Log-based Incremental Replication. [Click to skip ahead](#create-replication-schedule)." %}

          {% include integrations/databases/setup/binlog/log-based-replication-default-setting.html %}

      - title: "Create a replication schedule"
        anchor: "create-replication-schedule"
        content: |
          {% include integrations/shared-setup/replication-frequency.html %}

      - title: "Save the integration"
        anchor: "save-integration"
        content: |
          {% include shared/database-connection-settings.html type="finish-up" %}

  - title: "Select data to replicate"
    anchor: "sync-data"
    content: |
      {% include integrations/shared-setup/data-selection/object-selection.html %}


# -------------------------- #
#      Replication Info      #
# -------------------------- #

replication-sections:
  - content: |
      In this section:

      {% for section in page.replication-sections %}
      {% if section.title %}
      - [{{ section.summary | flatify }}](#{{ section.anchor }})
      {% endif %}
      {% endfor %}

  - title: "Extraction"
    anchor: "extraction-details"
    summary: "Details about Extraction, including object and data type discovery and selecting data for replication"
    content: |
      For every table set to replicate, Stitch will perform the following during Extraction:

      {% for subsection in section.subsections %}
      - [{{ subsection.summary | flatify }}](#{{ subsection.anchor }})
      {% endfor %}

    subsections:
      - title: "Discovery"
        anchor: "extraction--discovery"
        summary: "Discover table schemas and type discovered columns"
        content: |
          During Discovery, Stitch will:

          {% for sub-subsection in subsection.sub-subsections %}
          - [{{ sub-subsection.summary | flatify }}](#{{ sub-subsection.anchor }})
          {% endfor %}
        sub-subsections:
          - title: "Determining table schemas"
            anchor: "discovery--objects"
            summary: "Determine table schemas"
            content: |
              During this phase of Discovery, Stitch queries system tables to retrieve metadata about the objects the Stitch database user has access to. This metadata is used to determine which databases, tables, and columns to display in Stitch for replication.

              {{ site.data.taps.extraction.database-queries.postgres.structure-sync | flatify | markdownify }}

          - title: "Data typing"
            anchor: "discovery--data-types"
            summary: "Type the data in discovered columns"
            content: |
              Refer to the [{{ integration.display_name }} data types documentation]({{ postgres-overview.url | prepend: site.baseurl | append: "#data-types" }}) for more info about how {{ integration.display_name }} data is typed for selected columns.

      - title: "Data replication"
        anchor: "extraction--data-replication"
        summary: "Select records for replication"
        content: |
          During data replication, Stitch will query the selected tables and columns using the Replication Method defined for the table:

          {% assign replication-methods = site.data.taps.extraction.replication-methods %}

          {% for method in replication-methods.all %}
          - [{{ replication-methods[method.id]display-name }}]({{ replication-methods[method.id]documentation | flatify }})
          {% endfor %}
---
{% assign integration = page %}
{% include misc/data-files.html %}