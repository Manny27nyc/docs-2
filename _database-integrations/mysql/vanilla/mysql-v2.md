---
# -------------------------- #
#     USING THIS TEMPLATE    #
# -------------------------- #

## NEED HELP USING THIS TEMPLATE? SEE:
## https://docs-about-stitch-docs.netlify.com/reference/integration-templates/databases/
## FOR INSTRUCTIONS & REFERENCE INFO


# -------------------------- #
#      Page & Formatting     #
# -------------------------- #

title: MySQL (HP) (v2)
keywords: mysql, database integration, etl mysql, mysql etl
permalink: /integrations/databases/mysql/v2
summary: "Connect and replicate data from your MySQL database using Stitch's MySQL integration."

microsites:
  - title: "{{ page.display_name }} to Redshift"
    url: "http://mysql.toredshift.com/"
  - title: "{{ page.display_name }} to Postgres"
    url: "http://mysql.topostgres.com/"


key: "mysql-integration"

# -------------------------- #
#     Integration Details    #
# -------------------------- #

name: "mysql"
display_name: "MySQL"

singer: true
tap-name: "MySQL"
repo-url: "Not Applicable"

this-version: "2"

hosting-type: "generic" ## amazon, microsoft, google, etc.

driver: |
  [](){:target="new"}

# -------------------------- #
#       Stitch Details       #
# -------------------------- #

certified: true

frequency: "1 hour"
tier: "Standard"
port: 3306
db-type: "mysql"

## Stitch features

api-type: "platform.hp-mysql"
override-api-type: true
versions: "n/a"
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

log-based-replication-minimum-version: "5.6.2"
log-based-replication-master-instance: true
log-based-replication-read-replica: true

## Other Replication Methods

key-based-incremental-replication: true
full-table-replication: true

view-replication: true

# -------------------------- #
#      Feature Summary       #
# -------------------------- #

beta-copy: |
  {% assign all-mysql = site.database-integrations | where:"key","mysql-integration" %}
  {% assign mysql-overview = all-mysql | where:"content-type","database-category" | first %}
  
  **Note**: This version differs greatly than the previous version. Refer to the [Integration feature summary]({{ integration.url | prepend: site.baseurl | append: "#feature-summary" }}) and [version comparison documentation]({{ mysql-overview.url | prepend: site.baseurl | append: "#supported-features" }}) for more info.

feature-summary: |
  {% assign all-mysql = site.database-integrations | where:"key","mysql-integration" %}
  {% assign mysql-overview = all-mysql | where:"content-type","database-category" | first %}

  This version (v{{ integration.this-version }}) of Stitch's {{ integration.display_name }} integration optimizes replication by utilizing Avro schemas to write and validate data, thereby reducing the amount of time spent on data extraction and preparation. Compared to previous versions of the {{ integration.display_name }} integration, this version boasts increased performance and overall reduced replication time.

  Notable improvements and changes in this version also include:

  - **New column (field) naming rules.** Avro has specific rules that dictate how columns can be named. As a result, column names will be canonicalized to adhere to Avro rules and persisted to your destination using the Avro-friendly name. Refer to the [Column name transformations section](#data-replication--column-name-transformations) for more info.
  - **Improved handling of `JSON` data types**. In previous versions, these data types were treated as strings. This version will send them to your destination as JSON objects, which may result in [de-nesting]({{ link.destinations.storage.nested-structures | prepend: site.baseurl }}).
  
  **Note**: The following features aren't currently supported, but will be before the integration leaves beta: 
  
  - Custom SSL certificates and certificate authorities

  To get a look at how this version compares to the previous version of {{ integration.display_name }}, refer to the [{{ integration.display_name }} version comparison documentation]({{ mysql-overview.url | prepend: site.baseurl | append: "#supported-features" }}).

# -------------------------- #
#      Setup Requirements    #
# -------------------------- #

requirements-list:
  - item: |
      **The `CREATE USER` or `INSERT` privilege (for the `mysql` database).** The [`CREATE USER` privilege](https://dev.mysql.com/doc/refman/8.0/en/create-user.html){:target="new"} is required to create a database user for Stitch.
  - item: |
      **The `GRANT OPTION` privilege in {{ integration.display_name }}.** The [`GRANT OPTION` privilege](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_grant-option){:target="new"} is required to grant the necessary privileges to the Stitch database user.
  - item: |
      **The `SUPER` privilege in {{ integration.display_name }}.** If using binlog replication, the [`SUPER` privilege](https://dev.mysql.com/doc/refman/5.6/en/privileges-provided.html#priv_super){:target="new"} is required to define the appropriate server settings.


# -------------------------- #
#     Setup Instructions     #
# -------------------------- #

setup-steps:
  - title: "Verify your Stitch account's data pipeline region"
    anchor: "verify-stitch-account-region"
    content: |
      {% include shared/whitelisting-ips/locate-region-ip-addresses.html first-step=true %}

  - title: "Configure database connection settings"
    anchor: "connect-settings"
    content: |
      {% include integrations/templates/configure-connection-settings.html %}

  - title: "Configure Log-based Incremental Replication"
    anchor: "configure-log-based-incremental-replication"
    content: |
      {% include note.html type="single-line" content="**Note**: Skip this step if you're not planning to use Log-based Incremental Replication. [Click to skip ahead](#db-user)." %}

      {% include integrations/databases/setup/binlog/configure-server-settings-intro.html %}

      {% for substep in step.substeps %}
      - [Step 3.{{ forloop.index }}: {{ substep.title | flatify }}](#{{ substep.anchor }})
      {% endfor %}
    substeps:
      - title: "Configure server settings"
        anchor: "configure-database-server-settings"
        content: |
          In this step, you'll configure your {{ integration.display_name }} server to use Log-based Incremental Replication.
          
          {% include integrations/databases/setup/binlog/vanilla-mysql.html %}
      - title: "Retrieve server IDs"
        anchor: "server-id"
        content: |
          {% include integrations/databases/setup/binlog/mysql-server-id.html %}

  - title: "Create a Stitch database user"
    anchor: "db-user"
    content: |
      {% include note.html type="single-line" content="**Note**: You must have the `CREATE USER` and `GRANT OPTION` privileges to complete this step." %} 

      Next, you'll create a dedicated database user for Stitch. This will ensure Stitch is visible in any logs or audits, and allow you to maintain your privilege hierarchy.

      {% include integrations/templates/create-database-user-tabs.html %}

  - title: "Connect Stitch"
    anchor: "connect-stitch"
    content: |
      In this step, you'll complete the setup by entering the database's connection details and defining replication settings in Stitch.

      {% for substep in step.substeps %}
      - [Step 5.{{ forloop.index }}: {{ substep.title | flatify }}](#{{ substep.anchor }})
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
          {% include shared/database-connection-settings.html type="ssl" ssl-fields=true %}

      - title: "Define the Log-based Replication setting"
        anchor: "define-default-replication-method"
        content: |
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

              {{ site.data.taps.extraction.database-queries.mysql.structure-sync | flatify | markdownify }}

          - title: "Data typing"
            anchor: "discovery--data-types"
            summary: "Type the data in discovered columns"
            content: |
              Refer to the [{{ integration.display_name }} data types documentation]({{ mysql-overview.url | prepend: site.baseurl | append: "#data-types" }}) for more info about how {{ integration.display_name }} data is typed for selected columns.

      - title: "Data replication"
        anchor: "extraction--data-replication"
        summary: "Select records for replication"
        content: |
          During data replication, Stitch will:

          {% for sub-subsection in subsection.sub-subsections %}
          - [{{ sub-subsection.summary | flatify }}](#{{ sub-subsection.anchor }})
          {% endfor %}

        sub-subsections:
          - title: "Column name transformations"
            anchor: "data-replication--column-name-transformations"
            summary: "Transform column names to adhere to Avro rules"
            content: |
              To ensure column names are compatible with Avro, the integration will transform column names to adhere to Avro's rules. In Avro, [column names must](https://avro.apache.org/docs/current/spec.html#names){:target="new"}:

              - Start with one of the following:
                 - `A-Z`
                 - `a-z`
                 - `_` (underscore)
              - Contain only the following:
                 - Any characters in the list above (`A-Z`, `_`, etc)
                 - `0-9`

              If a column name contains an unsupported character, the integration will replace it with an underscore (`_`).
---
{% assign integration = page %}
{% include misc/data-files.html %}
