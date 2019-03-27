---
tap: "netsuite"
# version: "1.0"

name: "PromotionCode"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/PromotionCode.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "applyDiscountTo"
    type: "anything"
    description: ""

  - name: "code"
    type: "string"
    description: ""

  - name: "codePattern"
    type: "string"
    description: ""

  - name: "currencyList"
    type: "anything"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "customForm"
    type: "anything"
    description: ""

  - name: "description"
    type: "string"
    description: ""

  - name: "discount"
    type: "anything"
    description: ""

  - name: "discountType"
    type: "boolean, string"
    description: ""

  - name: "displayLineDiscounts"
    type: "boolean, string"
    description: ""

  - name: "endDate"
    type: "date-time"
    description: ""

  - name: "excludeItems"
    type: "boolean, string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "freeShipMethod"
    type: "anything"
    description: ""

  - name: "implementation"
    type: "anything"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "isPublic"
    type: "boolean, string"
    description: ""

  - name: "itemsList"
    type: "anything"
    description: ""

  - name: "locationList"
    type: "anything"
    description: ""

  - name: "minimumOrderAmount"
    type: "number, string"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "numberToGenerate"
    type: "integer, string"
    description: ""

  - name: "partnersList"
    type: "anything"
    description: ""

  - name: "rate"
    type: "string"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "useType"
    type: "anything"
    description: ""
---
