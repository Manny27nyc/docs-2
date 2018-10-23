---
tap: "netsuite"
# version: "10-15-2015"

name: "netsuite_item_account_mapping"
doc-link: https://system.netsuite.com/help/helpcenter/en_US/srbrowser/Browser2016_1/script/record/itemaccountmapping.html
description: |
  The `{{ table.name }}` table contains info about [PLACEHOLDER].

  {% include integrations/saas/netsuite-permission-list.html %}

replication-method: "Full Table"
primary-key: "internalId"
abstract: false

permissions:
  - name: "Item Account Mapping"
    level: "View"
    location: "Setup"
---