---
tap: "netsuite"
# version: "1.0"

name: "CouponCode"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/CouponCode.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "code"
    type: "string"
    description: ""

  - name: "dateSent"
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

  - name: "promotion"
    type: "anything"
    description: ""

  - name: "recipient"
    type: "anything"
    description: ""

  - name: "useCount"
    type: "integer, string"
    description: ""

  - name: "used"
    type: "boolean, string"
    description: ""
---
