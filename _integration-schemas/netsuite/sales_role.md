---
tap: "netsuite"
# version: "10-15-2015"

name: "netsuite_sales_role"
doc-link: https://system.netsuite.com/help/helpcenter/en_US/srbrowser/Browser2016_1/schema/search/salesrolesearchbasic.html?mode=package
description: |
  The `{{ table.name }}` table contains info about [PLACEHOLDER].

  {% include integrations/saas/netsuite-permission-list.html %}

replication-method: "Full Table"
primary-key: "internalId"
abstract: false

permissions:
  - name: "Sales Roles"
    level: "View"
    location: "Lists"
---