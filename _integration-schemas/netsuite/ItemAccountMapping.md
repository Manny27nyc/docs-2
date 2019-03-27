---
tap: "netsuite"
# version: "1.0"

name: "ItemAccountMapping"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/ItemAccountMapping.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "_class"
    type: "anything"
    description: ""

  - name: "accountingBook"
    type: "anything"
    description: ""

  - name: "customDimension"
    type: "anything"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "customForm"
    type: "anything"
    description: ""

  - name: "department"
    type: "anything"
    description: ""

  - name: "destinationAccount"
    type: "anything"
    description: ""

  - name: "effectiveDate"
    type: "date-time"
    description: ""

  - name: "endDate"
    type: "date-time"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "itemAccount"
    type: "anything"
    description: ""

  - name: "location"
    type: "anything"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "sourceAccount"
    type: "anything"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""
---
