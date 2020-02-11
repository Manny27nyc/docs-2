---
# -------------------------- #
#        CONTENT TYPE        #
# -------------------------- #

product-type: "connect"
content-type: "api-form"
form-type: "destination"
key: "destination-form-properties-databricks-delta-object"


# -------------------------- #
#        OBJECT INFO         #
# -------------------------- #

title: "Databricks Delta Destination Form Property"
api-type: "databricks_delta"
display-name: "Databricks Delta"

docs-name: "databricks-delta"
db-type: "databricks-delta"

description: |
  To set up an {{ form-property.display-name }} destination, users will need to:

  - TODO

  Refer to our [{{ form-property.display-name }} documentation]({{ link.destinations.setup.databricks-delta | prepend: site.baseurl }}) for additional details.


# -------------------------- #
#      OBJECT ATTRIBUTES     #
# -------------------------- #

uses-common-fields: false
object-attributes:
  - name: "staging_area"
    type: "string"
    required: true
    read-only: false
    description: |
      The name of the Amazon S3 bucket Stitch will stage data to before loading into {{ form-property.display-name }}.
    value: |
      "stitch-databricks-delta-bucket"

  - name: "access_token"
    type: "string"
    required: true
    read-only: false
    description: |
      A Databricks REST API access token. Refer to the [{{ form-property.display-name }} documentation]({{ link.destinations.setup.databricks-delta | append:"#generate-databricks-api-access-token" }}) for instructions on generating this credential.
    value: |
      "<ACCESS_TOKEN>"

  - name: "jdbc_url"
    type: "string"
    required: true
    read-only: false
    description: |
      Refer to the [{{ form-property.display-name }} documentation]({{ link.destinations.setup.databricks-delta | append:"#retrieve-jdbc-url" }}) for instructions on retrieving this info.
    value: |
      "TODO"
---