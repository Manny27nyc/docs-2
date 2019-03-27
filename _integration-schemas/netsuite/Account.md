---
tap: "netsuite"
version: "1.0"

name: "Account"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Account.json"
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

  - name: "acctName"
    type: "string"
    description: ""

  - name: "acctNumber"
    type: "string"
    description: ""

  - name: "acctType"
    type: "anything"
    description: ""

  - name: "billableExpensesAcct"
    type: "anything"
    description: ""

  - name: "cashFlowRate"
    type: "anything"
    description: ""

  - name: "category1099Misc"
    type: "anything"
    description: ""

  - name: "curDocNum"
    type: "integer, string"
    description: ""

  - name: "currency"
    type: "anything"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "deferralAcct"
    type: "anything"
    description: ""

  - name: "department"
    type: "anything"
    description: ""

  - name: "description"
    type: "string"
    description: ""

  - name: "eliminate"
    type: "boolean, string"
    description: ""

  - name: "exchangeRate"
    type: "string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "generalRate"
    type: "anything"
    description: ""

  - name: "includeChildren"
    type: "boolean, string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "inventory"
    type: "boolean, string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "legalName"
    type: "string"
    description: ""

  - name: "localizationsList"
    type: "anything"
    description: ""

  - name: "location"
    type: "anything"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "openingBalance"
    type: "number, string"
    description: ""

  - name: "parent"
    type: "anything"
    description: ""

  - name: "restrictToAccountingBookList"
    type: "anything"
    description: ""

  - name: "revalue"
    type: "boolean, string"
    description: ""

  - name: "subsidiaryList"
    type: "anything"
    description: ""

  - name: "tranDate"
    type: "date-time"
    description: ""

  - name: "unit"
    type: "anything"
    description: ""

  - name: "unitsType"
    type: "anything"
    description: ""
---
