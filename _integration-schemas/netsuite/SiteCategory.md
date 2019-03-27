---
tap: "netsuite"
# version: "1.0"

name: "SiteCategory"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/SiteCategory.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "categoryListLayout"
    type: "anything"
    description: ""

  - name: "correlatedItemsListLayout"
    type: "anything"
    description: ""

  - name: "description"
    type: "string"
    description: ""

  - name: "excludeFromSitemap"
    type: "boolean, string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "internalId"
    type: "string"
    description: ""

  - name: "isInactive"
    type: "boolean, string"
    description: ""

  - name: "isOnline"
    type: "boolean, string"
    description: ""

  - name: "itemId"
    type: "string"
    description: ""

  - name: "itemListLayout"
    type: "anything"
    description: ""

  - name: "metaTagHtml"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "pageTitle"
    type: "string"
    description: ""

  - name: "parentCategory"
    type: "anything"
    description: ""

  - name: "presentationItemList"
    type: "anything"
    description: ""

  - name: "relatedItemsListLayout"
    type: "anything"
    description: ""

  - name: "searchKeywords"
    type: "string"
    description: ""

  - name: "sitemapPriority"
    type: "anything"
    description: ""

  - name: "storeDetailedDescription"
    type: "string"
    description: ""

  - name: "storeDisplayImage"
    type: "anything"
    description: ""

  - name: "storeDisplayThumbnail"
    type: "anything"
    description: ""

  - name: "translationsList"
    type: "anything"
    description: ""

  - name: "urlComponent"
    type: "string"
    description: ""

  - name: "website"
    type: "anything"
    description: ""
---
