---
title: Take an Action Node
description: Placeholder
autotag-review: '2026-06-12T22:58:21.806Z'
TQID: 'https://experienceleague.adobe.com/uR-WvNz3gA6V7yyN3RRXH-MggrmGb1qvu1CBhMZRuAc'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: af7eab5e-3580-4254-9f56-3c20b4f6ef42
    internal-label: Journey Actions
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Take an action node

In a person journey, use an action on people when you want to apply a change to all people on the node path. For an account journey, this node type can be used within the split path by people or split path by accounts.

## Actions and constraints

| Action | Contraints |
| ------ | ---------- |
| **[!UICONTROL Send email]** | <li>Create email <li>Send-time optimization (optional) |
| **[!UICONTROL Change Data Value]** | <li>Select person attribute <li>Set new value |

## Add an action node {#add-an-action-node}

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

1. In the node properties on the right, select an action from the list and set any values for the action.

<!-- ![Person journey node - take an action](./assets/node-take-action-people.png){width="700" zoomable="yes"} -->

+++[!UICONTROL Send email]

Use this action to send an email. After you  create the email for the node, you can design, personalize, and preview email messages in the email design space (see [Email authoring](../content/email-authoring.md)).

<!-- ![Take an action - Send email](./assets/node-action-send-email-from-marketo.png){width="300"} -->

You can use [Send-time optimization](../marketing/email-send-time-optimization.md) to personalize email delivery timing by predicting when each profile is most likely to engage.

<!--
>[!NOTE]
>
>You can use email deduplication in account journeys to ensure that the same email is not sent multiple times to the same email address within a journey. For more information, see [Email deduplication](../content/email-deduplication.md).
-->

+++

+++[!UICONTROL Change data value]

Use this action to change the value of a people profile attribute in the database. Select the attribute and then set the new value.

<!-- ![Take an action - Update person profile](./assets/node-action-update-person-profile.png){width="300"} -->

+++
