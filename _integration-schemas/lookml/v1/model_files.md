---
tap: "lookml"
version: "1"
key: ""

name: "model_files"
doc-link: ""
singer-schema: "https://github.com/singer-io/tap-lookml/blob/master/tap_lookml/schemas/model_files.json"
description: |
  The `{{ table.name }}` table contains information about model files in your GitHub about using the Git API Search **filename** and **extension filters** for `model` and `lkml`.

replication-method: "Key-based Incremental"

api-method:
    name: "Git API Search"
    doc-link: "https://docs.github.com/en/rest/reference/search#search-code"

attributes:
  - name: "git_owner"
    type: "string"
    description: "The GitHub repository owner."

  - name: "git_repository"
    type: "string"
    description: "The GitHub repository."

  - name: "path"
    type: "string"
    description: "The URL for the repository."
      
  - name: "last_modified"
    type: "date-time"
    description: "The time the file was last modiefied."  

  - name: "content"
    type: "string"
    description: ""
  - name: "download_url"
    type: "string"
    description: ""
  - name: "encoding"
    type: "string"
    description: ""
  
  - name: "git_url"
    type: "string"
    description: ""
  - name: "html_url"
    type: "string"
    description: ""
  
  - name: "name"
    type: "string"
    description: ""
  
  - name: "sha"
    type: "string"
    description: ""
  - name: "size"
    type: "integer"
    description: ""
  - name: "type"
    type: "string"
    description: ""
  - name: "url"
    type: "string"
    description: ""
---
