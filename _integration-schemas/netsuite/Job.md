---
tap: "netsuite"
# version: "1.0"

name: "Job"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Job.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "accountNumber"
    type: "string"
    description: ""

  - name: "actualTime"
    type: "anything"
    description: ""

  - name: "addressbookList"
    type: "anything"
    description: ""

  - name: "allocatePayrollExpenses"
    type: "boolean, string"
    description: ""

  - name: "allowAllResourcesForTasks"
    type: "boolean, string"
    description: ""

  - name: "allowExpenses"
    type: "boolean, string"
    description: ""

  - name: "allowTime"
    type: "boolean, string"
    description: ""

  - name: "altName"
    type: "string"
    description: ""

  - name: "altPhone"
    type: "string"
    description: ""

  - name: "applyProjectExpenseTypeToAll"
    type: "boolean, string"
    description: ""

  - name: "billPay"
    type: "boolean, string"
    description: ""

  - name: "billingSchedule"
    type: "anything"
    description: ""

  - name: "calculatedEndDate"
    type: "date-time"
    description: ""

  - name: "calculatedEndDateBaseline"
    type: "date-time"
    description: ""

  - name: "category"
    type: "anything"
    description: ""

  - name: "comments"
    type: "string"
    description: ""

  - name: "companyName"
    type: "string"
    description: ""

  - name: "creditCardsList"
    type: "anything"
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

  - name: "dateCreated"
    type: "date-time"
    description: ""

  - name: "defaultAddress"
    type: "string"
    description: ""

  - name: "email"
    type: "string"
    description: ""

  - name: "emailPreference"
    type: "anything"
    description: ""

  - name: "endDate"
    type: "date-time"
    description: ""

  - name: "entityId"
    type: "string"
    description: ""

  - name: "entityStatus"
    type: "anything"
    description: ""

  - name: "estimateRevRecTemplate"
    type: "anything"
    description: ""

  - name: "estimatedCost"
    type: "number, string"
    description: ""

  - name: "estimatedGrossProfit"
    type: "number, string"
    description: ""

  - name: "estimatedGrossProfitPercent"
    type: "number, string"
    description: ""

  - name: "estimatedLaborCost"
    type: "number, string"
    description: ""

  - name: "estimatedLaborCostBaseline"
    type: "number, string"
    description: ""

  - name: "estimatedLaborRevenue"
    type: "number, string"
    description: ""

  - name: "estimatedRevenue"
    type: "number, string"
    description: ""

  - name: "estimatedTime"
    type: "anything"
    description: ""

  - name: "estimatedTimeOverride"
    type: "anything"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "fax"
    type: "string"
    description: ""

  - name: "fxRate"
    type: "number, string"
    description: ""

  - name: "globalSubscriptionStatus"
    type: "anything"
    description: ""

  - name: "includeCrmTasksInTotals"
    type: "boolean, string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isExemptTime"
    type: "boolean, string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "isProductiveTime"
    type: "boolean, string"
    description: ""

  - name: "isUtilizedTime"
    type: "boolean, string"
    description: ""

  - name: "jobBillingType"
    type: "anything"
    description: ""

  - name: "jobItem"
    type: "anything"
    description: ""

  - name: "jobPrice"
    type: "number, string"
    description: ""

  - name: "jobResourcesList"
    type: "anything"
    description: ""

  - name: "jobType"
    type: "anything"
    description: ""

  - name: "language"
    type: "anything"
    description: ""

  - name: "lastBaselineDate"
    type: "date-time"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "limitTimeToAssignees"
    type: "boolean, string"
    description: ""

  - name: "materializeTime"
    type: "boolean, string"
    description: ""

  - name: "milestonesList"
    type: "anything"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "openingBalance"
    type: "number, string"
    description: ""

  - name: "openingBalanceAccount"
    type: "anything"
    description: ""

  - name: "openingBalanceDate"
    type: "date-time"
    description: ""

  - name: "parent"
    type: "anything"
    description: ""

  - name: "percentComplete"
    type: "number, string"
    description: ""

  - name: "percentCompleteOverrideList"
    type: "anything"
    description: ""

  - name: "percentTimeComplete"
    type: "number, string"
    description: ""

  - name: "phone"
    type: "string"
    description: ""

  - name: "phoneticName"
    type: "string"
    description: ""

  - name: "plStatementList"
    type: "anything"
    description: ""

  - name: "projectExpenseType"
    type: "anything"
    description: ""

  - name: "projectedEndDate"
    type: "date-time"
    description: ""

  - name: "projectedEndDateBaseline"
    type: "date-time"
    description: ""

  - name: "revRecForecastRule"
    type: "anything"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "startDateBaseline"
    type: "date-time"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""

  - name: "timeRemaining"
    type: "anything"
    description: ""

  - name: "usePercentCompleteOverride"
    type: "boolean, string"
    description: ""

  - name: "workplace"
    type: "anything"
    description: ""
---
