---
# -------------------------- #
#          PAGE INFO         #
# -------------------------- #

title: Account Management
permalink: /account-security/
keywords: billing, plan, change plan, cancel, cancel account, delete, remove
summary: "Resources for everything account-related: Managing billing details, inviting team members, and more."
feedback: false

layout: general
key: "account-security"
content-type: "category-page"

level: "category"


# -------------------------- #
#       HOME PAGE DATA       #
# -------------------------- #

## Used to display info on the home page as a category tile

icon: "user-profile"
display-title: "Your Stitch account"
display-summary: "Set up and manage your Stitch account."
weight: 2

intro: |
  {{ page.summary }}

sections:
  - title: "Managing your account"
    anchor: "manage-your-account-category"
    type: "manage-your-account"
    additional-guides:
      - title: "Update Company Settings"
        url: "{{ link.account.account-settings }}#update-company-information"
        weight: 2

      - title: "Exploring Stitch Enterprise"
        url: "{{ link.account.enterprise-features }}"
        weight: 6
    content: |
      {% include layout/category-section-tiles.html %}

  - title: "Managing your team"
    anchor: "manage-your-team-category"
    type: "invite-your-team"
    additional-guides:
      - title: "Adding a team member"
        url: "{{ link.account.team-members }}#invite-team-member"
        weight: 2

      - title: "Adding a team member to multiple accounts"
        url: "{{ link.account.team-members }}#add-to-multiple-accounts"
        weight: 3

      - title: "Deactivating a team member"
        url: "{{ link.account.team-members }}#deactivate-team-member"
        weight: 4

      - title: "Troubleshooting account lockout"
        url: "{{ link.troubleshooting.troubleshoot-account-lockout }}"
        weight: 5
    content: |
      {% include layout/category-section-tiles.html %}

  - title: "Managing notifications"
    anchor: "manage-notifications-category"
    type: "notifications"
    content: |
      {% include layout/category-section-tiles.html %}

  - title: "Managing billing and row usage"
    anchor: "manage-row-usage-billing-category"
    type: "billing"
    additional-guides:
      - title: "Understanding integrations and plan types"
        url: "{{ link.billing.billing-faq }}#integrations"
        weight: 2

      - title: "Understanding historical data loads"
        url: "{{ link.billing.billing-faq }}#historical-data-loads"
        weight: 3

      - title: "Choosing and changing plans"
        url: "{{ link.billing.billing-faq }}#manage-plans"
        weight: 4

      - title: "Managing payment details and invoices"
        url: "{{ link.billing.billing-faq }}#payment-invoices"
        weight: 5

      - title: "Exploring Stitch Enterprise"
        url: "{{ link.account.enterprise-features }}"
        weight: 6

      - title: "Troubleshooting payment processing errors"
        url: "{{ link.troubleshooting.troubleshoot-payment-processing-errors }}"
        weight: 7
    content: |
      {% include layout/category-section-tiles.html %}

  - title: "Managing account security"
    anchor: "manage-account-security-category"
    type: "security"
    additional-guides:
      - title: "Compliance"
        url: "{{ link.security.faq }}#stitch-compliance"
        weight: 1

      - title: "Data access policies"
        url: "{{ link.security.faq }}#stitch-access"
        weight: 1

      - title: "Protocols and recommendations"
        url: "{{ link.security.faq }}#stitch-protocols-recommendations"
        weight: 1

      - title: "Reporting issues"
        url: "{{ link.security.faq }}#security-issues"
        weight: 6
    content: |
      {% include layout/category-section-tiles.html %}
---