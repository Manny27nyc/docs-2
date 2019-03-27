---
tap: "netsuite"
# version: "1.0"

name: "BillingAccount"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/BillingAccount.json"
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

  - name: "billingSchedule"
    type: "anything"
    description: ""

  - name: "cashSaleForm"
    type: "anything"
    description: ""

  - name: "createdBy"
    type: "string"
    description: ""

  - name: "createdDate"
    type: "date-time"
    description: ""

  - name: "currency"
    type: "anything"
    description: ""

  - name: "customFieldList"
    type: "anything"
    description: ""

  - name: "customForm"
    type: "anything"
    description: ""

  - name: "customer"
    type: "anything"
    description: ""

  - name: "customerDefault"
    type: "boolean, string"
    description: ""

  - name: "department"
    type: "anything"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "frequency"
    type: "anything"
    description: ""

  - name: "idNumber"
    type: "string"
    description: ""

  - name: "inactive"
    type: "boolean, string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "invoiceForm"
    type: "anything"
    description: ""

  - name: "lastBillCycleDate"
    type: "date-time"
    description: ""

  - name: "lastBillDate"
    type: "date-time"
    description: ""

  - name: "location"
    type: "anything"
    description: ""

  - name: "memo"
    type: "string"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nextBillCycleDate"
    type: "date-time"
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
---
