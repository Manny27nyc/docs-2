---
tap: "netsuite"
# version: "1.0"

name: "TaxGroup"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/TaxGroup.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "city"
    type: "string"
    description: ""

  - name: "county"
    type: "string"
    description: ""

  - name: "description"
    type: "string"
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

  - name: "piggyback"
    type: "boolean, string"
    description: ""

  - name: "rate"
    type: "number, string"
    description: ""

  - name: "state"
    type: "string"
    description: ""

  - name: "subsidiaryList"
    type: "anything"
    description: ""

  - name: "taxItemList"
    type: "anything"
    description: ""

  - name: "taxType"
    type: "anything"
    description: ""

  - name: "taxitem1"
    type: "anything"
    description: ""

  - name: "taxitem2"
    type: "anything"
    description: ""

  - name: "unitprice1"
    type: "string"
    description: ""

  - name: "unitprice2"
    type: "string"
    description: ""

  - name: "zip"
    type: "string"
    description: ""
---
