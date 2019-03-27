---
tap: "netsuite"
# version: "1.0"

name: "Deleted"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Deleted.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "customRecord"
    type: "boolean"
    description: ""

  - name: "deletedDate"
    type: "date-time"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "scriptId"
    type: "string"
    description: ""

  - name: "type"
    type: "string"
    description: ""
---
