---
# -------------------------- #
#      ENDPOINT DETAILS      #
# -------------------------- #

product-type: "connect"
content-type: "api-endpoint"
endpoint: "sources"
key: "unpause-a-source"
version: "4"


# -------------------------- #
#       METHOD DETAILS       #
# -------------------------- #

title: "Unpause a source"
method: "put"
short-url: |
  /v{{ endpoint.version }}{{ object.endpoint-url }}/{source_id}
full-url: |
  {{ api.base-url }}{{ endpoint.short-url | flatify }}
short: "{{ site.data.connect.core-objects.sources.pause.description }}"
description: |
  {{ site.data.connect.core-objects.sources.unpause.description }}

  **Note**: This endpoint behaves identically to [Update a source](#update-a-source).


# -------------------------- #
#       METHOD ARGUMENTS     #
# -------------------------- #

arguments:
  - name: "source_id"
    required: true
    type: "path parameter"
    description: "A path parameter corresponding to the unique ID of the source to be paused."
    example-value: |
      86741

  - name: "paused_at"
    required: false
    type: "null"
    description: |
      **To unpause a source**, this value must be `null`.
    example-value: |
      null


# -------------------------- #
#           RETURNS          #
# -------------------------- #

returns: |
  If successful, the API will return a status of <code class="api success">200 OK</code> and a [Source object]({{ site.data.connect.core-objects.sources.object }}) with a `null` `paused_at` value.


# ------------------------------ #
#   EXAMPLE REQUEST & RESPONSES  #
# ------------------------------ #

examples:
  - type: "Request"
    request-url: |
      {% assign right-bracket = "}" %}{{ endpoint.short-url | flatify | replace: "{source_id","86741" | remove: right-bracket | strip_newlines }}
    header: "{{ site.data.connect.request-headers.put.with-body | flatify }}"
    code: |
      '{
          "paused_at":null
      }'

  - type: "Response"
    code: |
      {
         "properties":{
            "anchor_time":"2019-01-30T18:16:37.205Z",
            "cron_expression":null,
            "frequency_in_minutes":"60",
            "image_version":"1.latest",
            "product":"pipeline",
            "shop":"stitchdatawearhouse",
            "start_date":"2017-01-01T00:00:00Z"
         },
         "updated_at":"2019-05-28T13:52:23Z",
         "schedule":null,
         "name":"shopify",
         "type":"platform.shopify",
         "deleted_at":null,
         "system_paused_at":null,
         "stitch_client_id":116078,
         "paused_at":null,
         "id":86741,
         "display_name":"Shopify",
         "created_at":"2019-01-10T19:38:18Z",
         "report_card":{
            "type":"platform.shopify",
            "current_step":1,
            "current_step_type":"fully_configured",
            "steps":[
               {
                  "type":"form",
                  "properties":[
                     {
                        "name":"anchor_time",
                        "is_required":false,
                        "is_credential":false,
                        "system_provided":false,
                        "property_type":"user_provided",
                        "json_schema":{
                           "type":"string",
                           "format":"date-time"
                        },
                        "provided":true,
                        "tap_mutable":false
                     },
                     {
                        "name":"cron_expression",
                        "is_required":false,
                        "is_credential":false,
                        "system_provided":false,
                        "property_type":"user_provided",
                        "json_schema":null,
                        "provided":false,
                        "tap_mutable":false
                     },
                     {
                        "name":"date_window_size",
                        "is_required":false,
                        "is_credential":false,
                        "system_provided":false,
                        "property_type":"user_provided",
                        "json_schema":{
                           "type":"integer"
                        },
                        "provided":false,
                        "tap_mutable":false
                     },
                     {
                        "name":"frequency_in_minutes",
                        "is_required":false,
                        "is_credential":false,
                        "system_provided":false,
                        "property_type":"user_provided",
                        "json_schema":{
                           "type":"string",
                           "pattern":"^1$|^30$|^60$|^360$|^720$|^1440$"
                        },
                        "provided":true,
                        "tap_mutable":false
                     },
                     {
                        "name":"image_version",
                        "is_required":true,
                        "is_credential":false,
                        "system_provided":true,
                        "property_type":"read_only",
                        "json_schema":null,
                        "provided":true,
                        "tap_mutable":false
                     },
                     {
                        "name":"shop",
                        "is_required":true,
                        "is_credential":false,
                        "system_provided":false,
                        "property_type":"user_provided",
                        "json_schema":{
                           "type":"string"
                        },
                        "provided":true,
                        "tap_mutable":false
                     },
                     {
                        "name":"start_date",
                        "is_required":true,
                        "is_credential":false,
                        "system_provided":false,
                        "property_type":"user_provided",
                        "json_schema":{
                           "type":"string",
                           "pattern":"^\\d{4}-\\d{2}-\\d{2}T00:00:00Z$"
                        },
                        "provided":true,
                        "tap_mutable":false
                     }
                  ]
               },
               {
                  "type":"oauth",
                  "properties":[
                     {
                        "name":"api_key",
                        "is_required":true,
                        "is_credential":true,
                        "system_provided":true,
                        "property_type":"system_provided_by_default",
                        "json_schema":{
                           "type":"string"
                        },
                        "provided":false,
                        "tap_mutable":false
                     }
                  ]
               },
               {
                  "type":"discover_schema",
                  "properties":[

                  ]
               },
               {
                  "type":"field_selection",
                  "properties":[

                  ]
               },
               {
                  "type":"fully_configured",
                  "properties":[

                  ]
               }
            ]
         }
      }
---