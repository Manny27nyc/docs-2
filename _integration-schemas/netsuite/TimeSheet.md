---
tap: "netsuite"
# version: "1.0"

name: "TimeSheet"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/TimeSheet.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "approvalStatus"
    type: "anything"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "customForm"
    type: "anything"
    description: ""

  - name: "employee"
    type: "anything"
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

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""

  - name: "timeGridList"
    type: "anything"
    description: ""

  - name: "totalHours"
    type: "anything"
    description: ""
---
