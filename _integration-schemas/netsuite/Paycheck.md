---
tap: "netsuite"
# version: "1.0"

name: "Paycheck"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Paycheck.json"
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

  - name: "account"
    type: "anything"
    description: ""

  - name: "address"
    type: "string"
    description: ""

  - name: "balance"
    type: "number, string"
    description: ""

  - name: "batchNumber"
    type: "string"
    description: ""

  - name: "createdDate"
    type: "date-time"
    description: ""

  - name: "department"
    type: "anything"
    description: ""

  - name: "entity"
    type: "anything"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "location"
    type: "anything"
    description: ""

  - name: "memo"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "payContribList"
    type: "anything"
    description: ""

  - name: "payDeductList"
    type: "anything"
    description: ""

  - name: "payDisburseList"
    type: "anything"
    description: ""

  - name: "payEarnList"
    type: "anything"
    description: ""

  - name: "payExpList"
    type: "anything"
    description: ""

  - name: "payFrequency"
    type: "string"
    description: ""

  - name: "payPtoList"
    type: "anything"
    description: ""

  - name: "paySummaryList"
    type: "anything"
    description: ""

  - name: "payTaxList"
    type: "anything"
    description: ""

  - name: "payTimeList"
    type: "anything"
    description: ""

  - name: "periodEnding"
    type: "date-time"
    description: ""

  - name: "postingPeriod"
    type: "anything"
    description: ""

  - name: "status"
    type: "string"
    description: ""

  - name: "tranDate"
    type: "date-time"
    description: ""

  - name: "tranId"
    type: "string"
    description: ""

  - name: "userAmount"
    type: "number, string"
    description: ""

  - name: "workplace"
    type: "anything"
    description: ""
---
