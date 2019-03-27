---
tap: "netsuite"
# version: "1.0"

name: "BillingSchedule"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/BillingSchedule.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "applyToSubtotal"
    type: "boolean, string"
    description: ""

  - name: "billForActuals"
    type: "boolean, string"
    description: ""

  - name: "dayPeriod"
    type: "integer, string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "frequency"
    type: "anything"
    description: ""

  - name: "inArrears"
    type: "boolean, string"
    description: ""

  - name: "initialAmount"
    type: "string"
    description: ""

  - name: "initialTerms"
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

  - name: "milestoneList"
    type: "anything"
    description: ""

  - name: "monthDom"
    type: "integer, string"
    description: ""

  - name: "monthDow"
    type: "anything"
    description: ""

  - name: "monthDowim"
    type: "anything"
    description: ""

  - name: "monthMode"
    type: "anything"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "numberRemaining"
    type: "integer, string"
    description: ""

  - name: "project"
    type: "anything"
    description: ""

  - name: "recurrenceDowMaskList"
    type: "anything"
    description: ""

  - name: "recurrenceList"
    type: "anything"
    description: ""

  - name: "recurrencePattern"
    type: "anything"
    description: ""

  - name: "recurrenceTerms"
    type: "anything"
    description: ""

  - name: "repeatEvery"
    type: "anything"
    description: ""

  - name: "scheduleType"
    type: "anything"
    description: ""

  - name: "seriesStartDate"
    type: "date-time"
    description: ""

  - name: "transaction"
    type: "anything"
    description: ""

  - name: "yearDom"
    type: "integer, string"
    description: ""

  - name: "yearDow"
    type: "anything"
    description: ""

  - name: "yearDowim"
    type: "anything"
    description: ""

  - name: "yearDowimMonth"
    type: "anything"
    description: ""

  - name: "yearMode"
    type: "anything"
    description: ""

  - name: "yearMonth"
    type: "anything"
    description: ""
---
