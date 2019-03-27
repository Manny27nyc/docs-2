---
tap: "netsuite"
# version: "1.0"

name: "File"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/File.json"
description: |
  The `{{ table.name }}` table contains info about 

replication-method: ""

api-method:
    name: ""
    doc-link: ""

attributes:
  - name: "_class"
    type: "string"
    description: ""

  - name: "altTagCaption"
    type: "string"
    description: ""

  - name: "attachFrom"
    type: "anything"
    description: ""

  - name: "bundleable"
    type: "boolean, string"
    description: ""

  - name: "caption"
    type: "string"
    description: ""

  - name: "content"
    type: "string"
    description: ""

  - name: "createdDate"
    type: "date-time"
    description: ""

  - name: "department"
    type: "string"
    description: ""

  - name: "description"
    type: "string"
    description: ""

  - name: "encoding"
    type: "anything"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "featuredDescription"
    type: "string"
    description: ""

  - name: "fileSize"
    type: "number, string"
    description: ""

  - name: "fileType"
    type: "anything"
    description: ""

  - name: "folder"
    type: "anything"
    description: ""

  - name: "hideInBundle"
    type: "boolean, string"
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

  - name: "isPrivate"
    type: "boolean, string"
    description: ""

  - name: "lastModifiedDate"
    type: "date-time"
    description: ""

  - name: "mediaFile"
    type: "anything"
    description: ""

  - name: "mediaTypeName"
    type: "string"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "owner"
    type: "anything"
    description: ""

  - name: "siteCategoryList"
    type: "anything"
    description: ""

  - name: "siteDescription"
    type: "string"
    description: ""

  - name: "storeDisplayThumbnail"
    type: "anything"
    description: ""

  - name: "textFileEncoding"
    type: "anything"
    description: ""

  - name: "url"
    type: "string"
    description: ""

  - name: "urlComponent"
    type: "string"
    description: ""
---
