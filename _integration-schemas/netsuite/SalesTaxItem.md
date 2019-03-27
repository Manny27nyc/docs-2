---
tap: "netsuite"
# version: "1.0"

name: "SalesTaxItem"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/SalesTaxItem.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "available"
    type: "anything"
    description: ""

  - name: "city"
    type: "string"
    description: ""

  - name: "county"
    type: "string"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "description"
    type: "string"
    description: ""

  - name: "displayName"
    type: "string"
    description: ""

  - name: "eccode"
    type: "boolean, string"
    description: ""

  - name: "effectiveFrom"
    type: "date-time"
    description: ""

  - name: "excludeFromTaxReports"
    type: "boolean, string"
    description: ""

  - name: "exempt"
    type: "boolean, string"
    description: ""

  - name: "export"
    type: "boolean, string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "includeChildren"
    type: "boolean, string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isDefault"
    type: "boolean, string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "itemId"
    type: "string"
    description: ""

  - name: "nexusCountry"
    type: "anything"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "parent"
    type: "anything"
    description: ""

  - name: "purchaseAccount"
    type: "anything"
    description: ""

  - name: "rate"
    type: "string"
    description: ""

  - name: "reverseCharge"
    type: "boolean, string"
    description: ""

  - name: "saleAccount"
    type: "anything"
    description: ""

  - name: "service"
    type: "boolean, string"
    description: ""

  - name: "state"
    type: "string"
    description: ""

  - name: "subsidiaryList"
    type: "anything"
    description: ""

  - name: "taxAccount"
    type: "anything"
    description: ""

  - name: "taxAgency"
    type: "anything"
    description: ""

  - name: "taxType"
    type: "anything"
    description: ""

  - name: "validUntil"
    type: "date-time"
    description: ""

  - name: "zip"
    type: "string"
    description: ""
---
