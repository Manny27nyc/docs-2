---
tap: "netsuite"
# version: "1.0"

name: "Folder"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-netsuite/blob/master/tap_netsuite/schemas/Folder.json"
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

  - name: "bundleable"
    type: "boolean, string"
    description: ""

  - name: "department"
    type: "anything"
    description: ""

  - name: "description"
    type: "string"
    description: ""

  - name: "externalId"
    type: "string"
    description: ""

  - name: "folderType"
    type: "anything"
    description: ""

  - name: "group"
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

  - name: "location"
    type: "anything"
    description: ""

  - name: "name"
    type: "string"
    description: ""

  - name: "nullFieldList"
    type: "anything"
    description: ""

  - name: "parent"
    type: "anything"
    description: ""

  - name: "subsidiary"
    type: "anything"
    description: ""
---
