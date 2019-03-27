---
tap: "netsuite"
version: "1.0"

name: "Transaction"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Transaction.json"
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

  - name: "_type"
    type: "string"
    description: ""

  - name: "accessibilityTypeFedEx"
    type: "anything"
    description: ""

  - name: "account"
    type: "anything"
    description: ""

  - name: "accountingApproval"
    type: "boolean, string"
    description: ""

  - name: "accountingBook"
    type: "anything"
    description: ""

  - name: "accountingBookDetailList"
    type: "anything"
    description: ""

  - name: "actualShipDate"
    type: "date-time"
    description: ""

  - name: "address"
    type: "string"
    description: ""

  - name: "adjLocation"
    type: "anything"
    description: ""

  - name: "advance"
    type: "number, string"
    description: ""

  - name: "altHandlingCost"
    type: "number, string"
    description: ""

  - name: "altSalesTotal"
    type: "number, string"
    description: ""

  - name: "altShippingCost"
    type: "number, string"
    description: ""

  - name: "amount"
    type: "number, string"
    description: ""

  - name: "amountPaid"
    type: "number, string"
    description: ""

  - name: "amountRemaining"
    type: "number, string"
    description: ""

  - name: "ancillaryEndorsementFedEx"
    type: "anything"
    description: ""

  - name: "apAcct"
    type: "anything"
    description: ""

  - name: "applied"
    type: "number, string"
    description: ""

  - name: "applyList"
    type: "anything"
    description: ""

  - name: "approvalStatus"
    type: "anything"
    description: ""

  - name: "approved"
    type: "boolean, string"
    description: ""

  - name: "arAcct"
    type: "anything"
    description: ""

  - name: "assemblyItem"
    type: "anything"
    description: ""

  - name: "authCode"
    type: "string"
    description: ""

  - name: "autoApply"
    type: "boolean, string"
    description: ""

  - name: "autoCalculateLag"
    type: "boolean, string"
    description: ""

  - name: "availableVendorCredit"
    type: "number, string"
    description: ""

  - name: "b13AFilingOptionFedEx"
    type: "anything"
    description: ""

  - name: "b13AStatementDataFedEx"
    type: "string"
    description: ""

  - name: "backupEmailAddressFedEx"
    type: "string"
    description: ""

  - name: "backupEmailAddressUps"
    type: "string"
    description: ""

  - name: "balance"
    type: "number, string"
    description: ""

  - name: "billAddressList"
    type: "anything"
    description: ""

  - name: "billOfMaterials"
    type: "anything"
    description: ""

  - name: "billOfMaterialsRevision"
    type: "anything"
    description: ""

  - name: "billPay"
    type: "boolean, string"
    description: ""

  - name: "billingAccount"
    type: "anything"
    description: ""

  - name: "billingAddress"
    type: "anything"
    description: ""

  - name: "billingSchedule"
    type: "anything"
    description: ""

  - name: "binNumbers"
    type: "string"
    description: ""

  - name: "blanketEndDateUps"
    type: "date-time"
    description: ""

  - name: "blanketStartDateUps"
    type: "date-time"
    description: ""

  - name: "bookingConfirmationNumFedEx"
    type: "string"
    description: ""

  - name: "buildable"
    type: "number, string"
    description: ""

  - name: "built"
    type: "number, string"
    description: ""

  - name: "canHaveStackable"
    type: "boolean, string"
    description: ""

  - name: "carrierIdUps"
    type: "string"
    description: ""

  - name: "cashBackList"
    type: "anything"
    description: ""

  - name: "ccApproved"
    type: "boolean, string"
    description: ""

  - name: "ccAvsStreetMatch"
    type: "anything"
    description: ""

  - name: "ccAvsZipMatch"
    type: "anything"
    description: ""

  - name: "ccExpireDate"
    type: "date-time"
    description: ""

  - name: "ccIsPurchaseCardBin"
    type: "boolean, string"
    description: ""

  - name: "ccName"
    type: "string"
    description: ""

  - name: "ccNumber"
    type: "string"
    description: ""

  - name: "ccProcessAsPurchaseCard"
    type: "boolean, string"
    description: ""

  - name: "ccSecurityCode"
    type: "string"
    description: ""

  - name: "ccSecurityCodeMatch"
    type: "anything"
    description: ""

  - name: "ccStreet"
    type: "string"
    description: ""

  - name: "ccZipCode"
    type: "string"
    description: ""

  - name: "chargeIt"
    type: "boolean, string"
    description: ""

  - name: "checkNum"
    type: "string"
    description: ""

  - name: "companyContributionList"
    type: "anything"
    description: ""

  - name: "companyTaxList"
    type: "anything"
    description: ""

  - name: "complete"
    type: "boolean, string"
    description: ""

  - name: "completedQuantity"
    type: "number, string"
    description: ""

  - name: "componentList"
    type: "anything"
    description: ""

  - name: "contribPct"
    type: "string"
    description: ""

  - name: "costComponentList"
    type: "anything"
    description: ""

  - name: "createdDate"
    type: "date-time"
    description: ""

  - name: "createdFrom"
    type: "anything"
    description: ""

  - name: "createdFromShipGroup"
    type: "integer, string"
    description: ""

  - name: "creditCard"
    type: "anything"
    description: ""

  - name: "creditCardProcessor"
    type: "anything"
    description: ""

  - name: "creditLimit"
    type: "number, string"
    description: ""

  - name: "creditList"
    type: "anything"
    description: ""

  - name: "currency"
    type: "anything"
    description: ""

  - name: "currencyName"
    type: "string"
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

  - name: "debitCardIssueNo"
    type: "string"
    description: ""

  - name: "deductionList"
    type: "anything"
    description: ""

  - name: "deferredRevenue"
    type: "number, string"
    description: ""

  - name: "depDate"
    type: "date-time"
    description: ""

  - name: "department"
    type: "anything"
    description: ""

  - name: "deposit"
    type: "anything"
    description: ""

  - name: "depositList"
    type: "anything"
    description: ""

  - name: "discountAmount"
    type: "number, string"
    description: ""

  - name: "discountDate"
    type: "date-time"
    description: ""

  - name: "discountItem"
    type: "anything"
    description: ""

  - name: "discountRate"
    type: "string"
    description: ""

  - name: "discountTotal"
    type: "number, string"
    description: ""

  - name: "drAccount"
    type: "anything"
    description: ""

  - name: "dueDate"
    type: "date-time"
    description: ""

  - name: "earningList"
    type: "anything"
    description: ""

  - name: "eccNumberUps"
    type: "string"
    description: ""

  - name: "email"
    type: "string"
    description: ""

  - name: "employee"
    type: "anything"
    description: ""

  - name: "employeeTaxList"
    type: "anything"
    description: ""

  - name: "endDate"
    type: "date-time"
    description: ""

  - name: "endOperation"
    type: "anything"
    description: ""

  - name: "entity"
    type: "anything"
    description: ""

  - name: "entityStatus"
    type: "anything"
    description: ""

  - name: "entityTaxRegNum"
    type: "anything"
    description: ""

  - name: "entryNumberUps"
    type: "string"
    description: ""

  - name: "estGrossProfit"
    type: "number, string"
    description: ""

  - name: "estGrossProfitPercent"
    type: "number, string"
    description: ""

  - name: "estimatedTotalValue"
    type: "number, string"
    description: ""

  - name: "exchangeRate"
    type: "number, string"
    description: ""

  - name: "excludeCommission"
    type: "boolean, string"
    description: ""

  - name: "expCostDiscAmount"
    type: "number, string"
    description: ""

  - name: "expCostDiscPrint"
    type: "boolean, string"
    description: ""

  - name: "expCostDiscRate"
    type: "string"
    description: ""

  - name: "expCostDiscTax1Amt"
    type: "number, string"
    description: ""

  - name: "expCostDiscTaxable"
    type: "boolean, string"
    description: ""

  - name: "expCostDiscount"
    type: "anything"
    description: ""

  - name: "expCostDiscprint"
    type: "boolean, string"
    description: ""

  - name: "expCostList"
    type: "anything"
    description: ""

  - name: "expCostTaxCode"
    type: "anything"
    description: ""

  - name: "expCostTaxRate1"
    type: "number, string"
    description: ""

  - name: "expCostTaxRate2"
    type: "number, string"
    description: ""

  - name: "expandAssembly"
    type: "boolean, string"
    description: ""

  - name: "expectedCloseDate"
    type: "date-time"
    description: ""

  - name: "expenseList"
    type: "anything"
    description: ""

  - name: "expirationDate"
    type: "date-time"
    description: ""

  - name: "exportTypeUps"
    type: "anything"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "fax"
    type: "string"
    description: ""

  - name: "firmed"
    type: "boolean, string"
    description: ""

  - name: "fob"
    type: "string"
    description: ""

  - name: "forecastType"
    type: "anything"
    description: ""

  - name: "fxAccount"
    type: "anything"
    description: ""

  - name: "generateIntegratedShipperLabel"
    type: "boolean, string"
    description: ""

  - name: "getAuth"
    type: "boolean, string"
    description: ""

  - name: "giftCert"
    type: "anything"
    description: ""

  - name: "giftCertApplied"
    type: "number, string"
    description: ""

  - name: "giftCertAvailable"
    type: "number, string"
    description: ""

  - name: "giftCertRedemptionList"
    type: "anything"
    description: ""

  - name: "giftCertTotal"
    type: "number, string"
    description: ""

  - name: "halAddr1FedEx"
    type: "string"
    description: ""

  - name: "halAddr2FedEx"
    type: "string"
    description: ""

  - name: "halAddr3FedEx"
    type: "string"
    description: ""

  - name: "halCityFedEx"
    type: "string"
    description: ""

  - name: "halCountryFedEx"
    type: "string"
    description: ""

  - name: "halPhoneFedEx"
    type: "string"
    description: ""

  - name: "halStateFedEx"
    type: "string"
    description: ""

  - name: "halZipFedEx"
    type: "string"
    description: ""

  - name: "handlingCost"
    type: "number, string"
    description: ""

  - name: "handlingTax1Rate"
    type: "number, string"
    description: ""

  - name: "handlingTax2Rate"
    type: "number, string"
    description: ""

  - name: "handlingTaxCode"
    type: "anything"
    description: ""

  - name: "hazmatTypeFedEx"
    type: "anything"
    description: ""

  - name: "holdAtLocationFedEx"
    type: "boolean, string"
    description: ""

  - name: "homeDeliveryDateFedEx"
    type: "date-time"
    description: ""

  - name: "homeDeliveryTypeFedEx"
    type: "anything"
    description: ""

  - name: "ignoreAvs"
    type: "boolean, string"
    description: ""

  - name: "inbondCodeUps"
    type: "string"
    description: ""

  - name: "inboundShipment"
    type: "anything"
    description: ""

  - name: "includeInForecast"
    type: "boolean, string"
    description: ""

  - name: "incoterm"
    type: "anything"
    description: ""

  - name: "insideDeliveryFedEx"
    type: "boolean, string"
    description: ""

  - name: "insidePickupFedEx"
    type: "boolean, string"
    description: ""

  - name: "intercoStatus"
    type: "anything"
    description: ""

  - name: "intercoTransaction"
    type: "anything"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "intlExemptionNumFedEx"
    type: "string"
    description: ""

  - name: "inventoryDetail"
    type: "anything"
    description: ""

  - name: "inventoryList"
    type: "anything"
    description: ""

  - name: "inventoryValue"
    type: "number, string"
    description: ""

  - name: "isBackflush"
    type: "boolean, string"
    description: ""

  - name: "isBookSpecific"
    type: "boolean, string"
    description: ""

  - name: "isCargoAircraftOnlyFedEx"
    type: "boolean, string"
    description: ""

  - name: "isMultiShipTo"
    type: "boolean, string"
    description: ""

  - name: "isRecurringPayment"
    type: "boolean, string"
    description: ""

  - name: "isRoutedExportTransactionUps"
    type: "boolean, string"
    description: ""

  - name: "isTaxable"
    type: "boolean, string"
    description: ""

  - name: "isWip"
    type: "boolean, string"
    description: ""

  - name: "item"
    type: "anything"
    description: ""

  - name: "itemCostDiscAmount"
    type: "number, string"
    description: ""

  - name: "itemCostDiscPrint"
    type: "boolean, string"
    description: ""

  - name: "itemCostDiscRate"
    type: "string"
    description: ""

  - name: "itemCostDiscTax1Amt"
    type: "number, string"
    description: ""

  - name: "itemCostDiscTaxable"
    type: "boolean, string"
    description: ""

  - name: "itemCostDiscount"
    type: "anything"
    description: ""

  - name: "itemCostList"
    type: "anything"
    description: ""

  - name: "itemCostTaxCode"
    type: "anything"
    description: ""

  - name: "itemCostTaxRate1"
    type: "number, string"
    description: ""

  - name: "itemCostTaxRate2"
    type: "number, string"
    description: ""

  - name: "itemFulfillment"
    type: "anything"
    description: ""

  - name: "itemList"
    type: "anything"
    description: ""

  - name: "job"
    type: "anything"
    description: ""

  - name: "landedCostMethod"
    type: "anything"
    description: ""

  - name: "landedCostPerLine"
    type: "boolean, string"
    description: ""

  - name: "landedCostsList"
    type: "anything"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "leadSource"
    type: "anything"
    description: ""

  - name: "licenseDateUps"
    type: "date-time"
    description: ""

  - name: "licenseExceptionUps"
    type: "anything"
    description: ""

  - name: "licenseNumberUps"
    type: "string"
    description: ""

  - name: "lineList"
    type: "anything"
    description: ""

  - name: "linkedTrackingNumbers"
    type: "string"
    description: ""

  - name: "location"
    type: "anything"
    description: ""

  - name: "manufacturingRouting"
    type: "anything"
    description: ""

  - name: "memo"
    type: "string"
    description: ""

  - name: "message"
    type: "string"
    description: ""

  - name: "messageSel"
    type: "anything"
    description: ""

  - name: "methodOfTransportUps"
    type: "anything"
    description: ""

  - name: "nextApprover"
    type: "anything"
    description: ""

  - name: "nextBill"
    type: "date-time"
    description: ""

  - name: "nexus"
    type: "anything"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "onCreditHold"
    type: "string"
    description: ""

  - name: "oneTime"
    type: "number, string"
    description: ""

  - name: "operationList"
    type: "anything"
    description: ""

  - name: "opportunity"
    type: "anything"
    description: ""

  - name: "options"
    type: "anything"
    description: ""

  - name: "orderQuantity"
    type: "number, string"
    description: ""

  - name: "orderStatus"
    type: "anything"
    description: ""

  - name: "otherList"
    type: "anything"
    description: ""

  - name: "otherRefNum"
    type: "string"
    description: ""

  - name: "packageFedExList"
    type: "anything"
    description: ""

  - name: "packageList"
    type: "anything"
    description: ""

  - name: "packageUpsList"
    type: "anything"
    description: ""

  - name: "packageUspsList"
    type: "anything"
    description: ""

  - name: "packedDate"
    type: "date-time"
    description: ""

  - name: "parentExpenseAlloc"
    type: "anything"
    description: ""

  - name: "partiesToTransactionUps"
    type: "boolean, string"
    description: ""

  - name: "partner"
    type: "anything"
    description: ""

  - name: "partnersList"
    type: "anything"
    description: ""

  - name: "payPalAuthId"
    type: "string"
    description: ""

  - name: "payPalProcess"
    type: "boolean, string"
    description: ""

  - name: "payPalStatus"
    type: "string"
    description: ""

  - name: "payPalTranId"
    type: "string"
    description: ""

  - name: "payment"
    type: "number, string"
    description: ""

  - name: "paymentEventDate"
    type: "date-time"
    description: ""

  - name: "paymentEventHoldReason"
    type: "anything"
    description: ""

  - name: "paymentEventResult"
    type: "anything"
    description: ""

  - name: "paymentEventType"
    type: "anything"
    description: ""

  - name: "paymentEventUpdatedBy"
    type: "string"
    description: ""

  - name: "paymentHold"
    type: "boolean, string"
    description: ""

  - name: "paymentList"
    type: "anything"
    description: ""

  - name: "paymentMethod"
    type: "anything"
    description: ""

  - name: "paypalAuthId"
    type: "string"
    description: ""

  - name: "paypalProcess"
    type: "boolean, string"
    description: ""

  - name: "pending"
    type: "number, string"
    description: ""

  - name: "pickedDate"
    type: "date-time"
    description: ""

  - name: "pnRefNum"
    type: "string"
    description: ""

  - name: "postingPeriod"
    type: "anything"
    description: ""

  - name: "printVoucher"
    type: "boolean, string"
    description: ""

  - name: "probability"
    type: "number, string"
    description: ""

  - name: "promoCode"
    type: "anything"
    description: ""

  - name: "promotionsList"
    type: "anything"
    description: ""

  - name: "purchaseContract"
    type: "anything"
    description: ""

  - name: "purchaseOrderList"
    type: "anything"
    description: ""

  - name: "quantity"
    type: "number, string"
    description: ""

  - name: "recipientTaxIdUps"
    type: "string"
    description: ""

  - name: "recognizedRevenue"
    type: "number, string"
    description: ""

  - name: "recurAnnually"
    type: "number, string"
    description: ""

  - name: "recurMonthly"
    type: "number, string"
    description: ""

  - name: "recurQuarterly"
    type: "number, string"
    description: ""

  - name: "recurWeekly"
    type: "number, string"
    description: ""

  - name: "recurringBill"
    type: "boolean, string"
    description: ""

  - name: "refundCheck"
    type: "boolean, string"
    description: ""

  - name: "requestedBy"
    type: "anything"
    description: ""

  - name: "revCommitStatus"
    type: "anything"
    description: ""

  - name: "revRecEndDate"
    type: "date-time"
    description: ""

  - name: "revRecOnRevCommitment"
    type: "boolean, string"
    description: ""

  - name: "revRecSchedule"
    type: "anything"
    description: ""

  - name: "revRecStartDate"
    type: "date-time"
    description: ""

  - name: "revenueStatus"
    type: "anything"
    description: ""

  - name: "reversalDate"
    type: "date-time"
    description: ""

  - name: "reversalDefer"
    type: "boolean, string"
    description: ""

  - name: "reversalEntry"
    type: "string"
    description: ""

  - name: "revision"
    type: "anything"
    description: ""

  - name: "salesEffectiveDate"
    type: "date-time"
    description: ""

  - name: "salesGroup"
    type: "anything"
    description: ""

  - name: "salesOrder"
    type: "anything"
    description: ""

  - name: "salesRep"
    type: "anything"
    description: ""

  - name: "salesTeamList"
    type: "anything"
    description: ""

  - name: "saturdayDeliveryFedEx"
    type: "boolean, string"
    description: ""

  - name: "saturdayDeliveryUps"
    type: "boolean, string"
    description: ""

  - name: "saturdayPickupFedex"
    type: "boolean, string"
    description: ""

  - name: "saveOnAuthDecline"
    type: "boolean, string"
    description: ""

  - name: "schedulingMethod"
    type: "anything"
    description: ""

  - name: "scrapQuantity"
    type: "number, string"
    description: ""

  - name: "sendBackupEmailFedEx"
    type: "boolean, string"
    description: ""

  - name: "sendBackupEmailUps"
    type: "boolean, string"
    description: ""

  - name: "sendShipNotifyEmailFedEx"
    type: "boolean, string"
    description: ""

  - name: "sendShipNotifyEmailUps"
    type: "boolean, string"
    description: ""

  - name: "serialNumbers"
    type: "string"
    description: ""

  - name: "shipAddress"
    type: "string"
    description: ""

  - name: "shipAddressList"
    type: "anything"
    description: ""

  - name: "shipComplete"
    type: "boolean, string"
    description: ""

  - name: "shipDate"
    type: "date-time"
    description: ""

  - name: "shipDateFedEx"
    type: "date-time"
    description: ""

  - name: "shipGroupList"
    type: "anything"
    description: ""

  - name: "shipIsResidential"
    type: "boolean, string"
    description: ""

  - name: "shipMethod"
    type: "anything"
    description: ""

  - name: "shipNotifyEmailAddress2Ups"
    type: "string"
    description: ""

  - name: "shipNotifyEmailAddressFedEx"
    type: "string"
    description: ""

  - name: "shipNotifyEmailAddressUps"
    type: "string"
    description: ""

  - name: "shipNotifyEmailMessageUps"
    type: "string"
    description: ""

  - name: "shipStatus"
    type: "anything"
    description: ""

  - name: "shipTo"
    type: "anything"
    description: ""

  - name: "shipmentWeightFedEx"
    type: "number, string"
    description: ""

  - name: "shipmentWeightUps"
    type: "number, string"
    description: ""

  - name: "shippedDate"
    type: "date-time"
    description: ""

  - name: "shippingAddress"
    type: "anything"
    description: ""

  - name: "shippingCost"
    type: "number, string"
    description: ""

  - name: "shippingTax1Rate"
    type: "number, string"
    description: ""

  - name: "shippingTax2Rate"
    type: "number, string"
    description: ""

  - name: "shippingTaxCode"
    type: "anything"
    description: ""

  - name: "shopperIpAddress"
    type: "string"
    description: ""

  - name: "signatureHomeDeliveryFedEx"
    type: "boolean, string"
    description: ""

  - name: "softDescriptor"
    type: "string"
    description: ""

  - name: "source"
    type: "string"
    description: ""

  - name: "sourceTransactionId"
    type: "string"
    description: ""

  - name: "sourceTransactionLine"
    type: "integer, string"
    description: ""

  - name: "specialOrder"
    type: "boolean, string"
    description: ""

  - name: "startDate"
    type: "date-time"
    description: ""

  - name: "startOperation"
    type: "anything"
    description: ""

  - name: "status"
    type: "string"
    description: ""

  - name: "subTotal"
    type: "number, string"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""

  - name: "subsidiaryTaxRegNum"
    type: "anything"
    description: ""

  - name: "supervisorApproval"
    type: "boolean, string"
    description: ""

  - name: "syncPartnerTeams"
    type: "boolean, string"
    description: ""

  - name: "syncSalesTeams"
    type: "boolean, string"
    description: ""

  - name: "tax1Amt"
    type: "number, string"
    description: ""

  - name: "tax2Amt"
    type: "number, string"
    description: ""

  - name: "tax2Total"
    type: "number, string"
    description: ""

  - name: "taxDetailsList"
    type: "anything"
    description: ""

  - name: "taxDetailsOverride"
    type: "boolean, string"
    description: ""

  - name: "taxItem"
    type: "anything"
    description: ""

  - name: "taxRate"
    type: "number, string"
    description: ""

  - name: "taxRegOverride"
    type: "boolean, string"
    description: ""

  - name: "taxTotal"
    type: "number, string"
    description: ""

  - name: "terms"
    type: "anything"
    description: ""

  - name: "termsFreightChargeFedEx"
    type: "number, string"
    description: ""

  - name: "termsInsuranceChargeFedEx"
    type: "number, string"
    description: ""

  - name: "termsOfSaleFedEx"
    type: "anything"
    description: ""

  - name: "thirdPartyAcctFedEx"
    type: "string"
    description: ""

  - name: "thirdPartyAcctUps"
    type: "string"
    description: ""

  - name: "thirdPartyCountryFedEx"
    type: "anything"
    description: ""

  - name: "thirdPartyCountryUps"
    type: "anything"
    description: ""

  - name: "thirdPartyTypeFedEx"
    type: "anything"
    description: ""

  - name: "thirdPartyTypeUps"
    type: "anything"
    description: ""

  - name: "thirdPartyZipcodeUps"
    type: "string"
    description: ""

  - name: "threeDStatusCode"
    type: "string"
    description: ""

  - name: "timeDiscAmount"
    type: "number, string"
    description: ""

  - name: "timeDiscPrint"
    type: "boolean, string"
    description: ""

  - name: "timeDiscRate"
    type: "string"
    description: ""

  - name: "timeDiscTax1Amt"
    type: "number, string"
    description: ""

  - name: "timeDiscTaxable"
    type: "boolean, string"
    description: ""

  - name: "timeDiscount"
    type: "anything"
    description: ""

  - name: "timeList"
    type: "anything"
    description: ""

  - name: "timeTaxCode"
    type: "anything"
    description: ""

  - name: "timeTaxRate1"
    type: "number, string"
    description: ""

  - name: "timeTaxRate2"
    type: "number, string"
    description: ""

  - name: "title"
    type: "string"
    description: ""

  - name: "toAch"
    type: "boolean, string"
    description: ""

  - name: "toBeEmailed"
    type: "boolean, string"
    description: ""

  - name: "toBeFaxed"
    type: "boolean, string"
    description: ""

  - name: "toBePrinted"
    type: "boolean, string"
    description: ""

  - name: "toPrint2"
    type: "boolean, string"
    description: ""

  - name: "toSubsidiary"
    type: "anything"
    description: ""

  - name: "total"
    type: "number, string"
    description: ""

  - name: "totalCostEstimate"
    type: "number, string"
    description: ""

  - name: "trackingNumbers"
    type: "string"
    description: ""

  - name: "tranDate"
    type: "date-time"
    description: ""

  - name: "tranId"
    type: "string"
    description: ""

  - name: "tranIsVsoeBundle"
    type: "boolean, string"
    description: ""

  - name: "transactionNumber"
    type: "string"
    description: ""

  - name: "transferLocation"
    type: "anything"
    description: ""

  - name: "unApplied"
    type: "number, string"
    description: ""

  - name: "unapplied"
    type: "number, string"
    description: ""

  - name: "undepFunds"
    type: "boolean, string"
    description: ""

  - name: "unitCost"
    type: "number, string"
    description: ""

  - name: "units"
    type: "anything"
    description: ""

  - name: "unitsType"
    type: "anything"
    description: ""

  - name: "useItemCostAsTransferCost"
    type: "boolean, string"
    description: ""

  - name: "useMultiCurrency"
    type: "boolean, string"
    description: ""

  - name: "userTaxTotal"
    type: "number, string"
    description: ""

  - name: "userTotal"
    type: "number, string"
    description: ""

  - name: "validFrom"
    type: "date-time"
    description: ""

  - name: "vatRegNum"
    type: "string"
    description: ""

  - name: "visibleToCustomer"
    type: "boolean, string"
    description: ""

  - name: "voidJournal"
    type: "anything"
    description: ""

  - name: "vsoeAutoCalc"
    type: "boolean, string"
    description: ""
---
