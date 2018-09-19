---
tap: "netsuite"
# version: "10-15-2015"

name: "netsuite_item_supply_plan"
doc-link: https://system.netsuite.com/help/helpcenter/en_US/srbrowser/Browser2016_1/script/record/itemsupplyplan.html
description: |
  The `{{ table.name }}` table contains info about [PLACEHOLDER].

  {% include integrations/saas/netsuite-permission-list.html %}

replication-method: "Incremental"
primary-key: "internalId"
replication-key: "lastModifiedDate"

abstract: false

permissions:
  - name: "Item Supply Plan"
    level: "View"
    location: "Lists"
---