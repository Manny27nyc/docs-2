---
content-type: "api-form"
form-type: "source"
key: "source-form-properties-marketo-object"

title: "Marketo Source Form Property"
description: "{{ api.form-properties.source-forms.marketo.description }}"

deprecated:
  as-of: "June 26, 2018"
  use-instead: "[Marketo Bulk]({{ api.form-properties.source-forms.marketo-bulk.section }})"

object-attributes:
  - name: "client_id"
    type: "string"
    required: true
    description: "The user's Marketo client ID."

  - name: "client_secret"
    type: "string"
    required: true
    description: "The user's Marketo client secret."

  - name: "frequency_in_minutes"
    type: "string"
    required: true
    description: |
      {{ connect.common.attributes.frequency | replace: "[INTEGRATION]","Marketo" }}

  - name: "endpoint"
    type: "string"
    required: true
    description: "The user's Marketo REST endpoint URL. For example: `https://457-RFG-234.mktorest.com/rest`"

  - name: "identity"
    type: "string"
    required: true
    description: "The user's Marketo REST identity URL. For example: `https://457-RFG-234.mktorest.com/identity`"

  - name: "max_daily_calls"
    type: "string"
    required: false
    description: "The maximum number of daily API calls that Stitch may make to the Marketo API."

  - name: "start_date"
    type: "string"
    required: true
    description: |
      {{ connect.common.attributes.start-date replace: "[INTEGRATION]","Marketo" }}

examples: 
  - code: |
      {  
       "type":"platform.marketo",
       "properties":{
          "client_id":"<CLIENT_ID>",
          "client_secret":"<CLIENT_SECRET>",
          "frequency_in_minutes":"1440",
          "endpoint":"https://457-RFG-234.mktorest.com/rest",
          "identity":"https://457-RFG-234.mktorest.com/identity",
          "max_daily_calls":"8,000",
          "start_date":"2018-01-10T00:00:00Z"
        }
      }
---