---
# -------------------------- #
#          PAGE INFO         #
# -------------------------- #

title: Destination and Source API Availability Reference
permalink: /developers/stitch-connect/guides/source-destination-reference
summary: "Current API availability for Stitch's destinations and sources."

product-type: "connect"
content-type: "guide"
content-id: &key "connect-connection-reference"

key: "connect-connection-reference"

layout: general
sidebar: on-page


# -------------------------- #
#      GUIDE PAGE INFO       #
# -------------------------- #

## This is used only on the /stitch-connect/guides page.
doc-type: "reference"
icon: source
order: 10

description: "Current API availability for Stitch's destinations and sources."


# -------------------------- #
#   RELATED SIDEBAR LINKS    #
# -------------------------- #

related:
  - title: "All destinations"
    link: "{{ site.baseurl }}/destinations"

  - title: "All integrations"
    link: "{{ site.baseurl }}/integrations"
    
  - title: "Connect API reference"
    link: "{{ link.connect.api | prepend: site.baseurl }}"

  - title: "All Connect guides"
    link: "{{ link.connect.guides.category | prepend: site.baseurl }}"


# -------------------------- #
#         GUIDE INTRO        #
# -------------------------- #

intro: |
  {% include misc/data-files.html %}
  {% include misc/icons.html %}

  This guide serves as a reference for API availability for Stitch's destinations and sources.

  {% for section in page.sections %}
  - [{{ section.title }}](#{{ section.anchor }})
  {% endfor %}


# -------------------------- #
#        GUIDE CONTENT       #
# -------------------------- #


sections:
  - title: "Destination API availability"
    anchor: "destinations-api-availability"
# The logic in this section uses the destination setup guides to
# create rows in the table. Doing this because there aren't dedicated
# pages for each 'branded' type of destination, and this is
# currently the only way to get everything without hard coding it.
    content: |
      In the table below:

      - **Destination name**: The name of the destination and a link to its setup guide.
      - **API availability**: Indicates if the destination is available via the API. {{ supported | replace:"TOOLTIP","Available in Connect" }} indicates that the destination is supported; {{ not-supported | replace:"TOOLTIP","Not available in Connect" }} indicates the destination isn't supported.
      - **API connection property**: If the destination is supported, this column will contain the name of the destination's corresponding API [destination connection property]({{ link.connect.api | prepend: site.baseurl | append: site.data.connect.data-structures.destination-form-properties.section }}). Use this info to create the destination using the [Create a destination endpoint]({{ link.connect.api | prepend: site.baseurl | append: site.data.connect.core-objects.destinations.create.anchor }}).

      {% assign destinations = site.destinations | where:"content-type","destination-setup" | sort_natural:"display_name" %}
      {% assign form-properties = site.developer-files | where:"content-type","api-form" %}
      {% assign forms-of-type = form-properties | where:"form-type","destination" | sort_natural:"display-name" %}

      <table class="attribute-list">
      <tr>
      <td width="35%; fixed">
      <strong>Destination name</strong>
      </td>
      <td>
      <strong>API availability</strong>
      </td>
      <td>
      <strong>API connection property</strong>
      </td>
      </tr>
      {% for destination in destinations %}
      {% if destination.key contains "setup" %}
        {% assign latest-version = site.data.destinations[destination.type]versions.latest-version %}
        {% assign version = "v" | append: latest-version %}

      {% if destination.this-version == latest-version %}
      <tr>
      <td>
      <a href="{{ destination.url | prepend: site.baseurl }}">
      {{ destination.display_name }}
      </a>
      </td>

      <td>
      {% if site.data.destinations[destination.type]stitch-details.api-type or site.data.destinations[destination.type][version]stitch-details.api-type %}

      {% if site.data.destinations[destination.type]stitch-details.api-type %}
      {% assign api-type = site.data.destinations[destination.type]stitch-details.api-type %}
      {% else %}
      {% assign api-type = site.data.destinations[destination.type][version]stitch-details.api-type %}
      {% endif %}

      {{ supported | replace:"TOOLTIP","Available in Connect" }} Available
      </td>
      <td>
      {% assign form-property = forms-of-type | where:"api-type",api-type | first %}
      <a href="{{ link.connect.api | prepend: site.baseurl | append:"#" | append:form-property.key }}">{{ form-property.api-type }}</a>
      </td>
      
      {% else %}

      {{ not-supported | replace:"TOOLTIP","Not available in Connect" }} Not available
      </td>
      <td>
      </td>
      {% endif %}

      </tr>
      {% endif %}
      {% endif %}
      {% endfor %}

  - title: "Source API availability"
    anchor: "sources-api-availability"
    content: |
      In the table below:

      - **Source name**: The name of the source and a link to its setup guide.
      - **API availability**: Indicates if the source is available via the API. {{ supported | replace:"TOOLTIP","Available in Connect" }} indicates that the source is supported; {{ not-supported | replace:"TOOLTIP","Not available in Connect" }} indicates the source isn't supported.
      - **API connection property**: If the source is supported, this column will contain the name of the source's corresponding API [source connection property]({{ link.connect.api | prepend: site.baseurl | append: site.data.connect.data-structures.source-form-properties.section }}). Use this info to create the source using the [Create a source endpoint]({{ link.connect.api | prepend: site.baseurl | append: site.data.connect.core-objects.sources.create.anchor }}).

      {% capture table %}
      {% assign form-properties = site.developer-files | where:"content-type","api-form" %}
      {% assign forms-of-type = form-properties | where:"form-type","source" | sort:"display-name" %}
      {% assign all-connections = site.documents | where:"input",true | sort:"display_name" %}

      <table class="attribute-list" id="filter-table">
      <tr>
      <th align="right" width="35%; fixed">
      <strong>Source name</strong>
      </th>
      <th>
      <strong>API availability</strong>
      </th>
      <th>
      <strong>API connection property</strong>
      </th>
      </tr>
      <tbody id="filter-body">
      {% for connection in all-connections %}

      {% if connection.db-type %}
      {% assign latest-version = site.data.taps.versions[connection.db-type]latest-version %}

      {% else %}
      {% assign latest-version = site.data.taps.versions[connection.name]latest-version %}
      {% endif %}

      {% if connection.this-version == latest-version or connection.override-api-type == true %}
      <tr>
      <td>
      <a href="{{ connection.url | prepend: site.baseurl }}">
      {{ connection.display_name }}
      </a>
      </td>
      <td>
      {% if connection.api-type %}
      {{ supported | replace:"TOOLTIP","Available in Connect" }} Available
      </td>
      <td>
      {% assign form-property = forms-of-type | where:"api-type",connection.api-type | first %}
      <a href="{{ link.connect.api | prepend: site.baseurl | append:"#" | append:form-property.key }}">{{ form-property.api-type }}</a>
      </td>
      {% else %}

      {{ not-supported | replace:"TOOLTIP","Not available in Connect" }} Not available
      </td>
      <td>
      </td>
      {% endif %}
      </tr>
      {% endif %}
      {% endfor %}
      <tr id="noConnectionYet" style="display: none">
      <td id="noConnectionYetName" colspan="3" align="center">
        <strong>Don't see the source you want?</strong> <a href="mailto:{{site.support}}">Let us know</a>!
      </td>
      </tr>
      </tbody>
      </table>
      {% endcapture %}

      {% include layout/on-page-search/table-search.html placeholder-copy="Find a source connection property" table=table %}
---