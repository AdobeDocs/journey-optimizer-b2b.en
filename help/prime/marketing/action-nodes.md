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

In a person journey, use an action on people when you want to apply a change to all people on the node path.

## Actions and constraints {#actions}

| Action | Constraints |
| ------ | ----------- |
| **[!UICONTROL Activate to destination]** | <li>Select or create a static list <li>If the list does not have an activated estination, activate the list |
| **[!UICONTROL Add Person to Journey]** | <li>Select a scheduled or live journey <li>Audience criteria of the target journey is not applied |
| **[!UICONTROL Add To List]** | <li>Create a new static list or select an existing one |
| **[!UICONTROL Add to Marketo List]** | <li>Select a static list in Marketo Engage |
| **[!UICONTROL Change Data Value]** | <li>Select person attribute <li>Set new value |
| **[!UICONTROL Change Program Data]** | <li>Select program attribute <li>Set new value |
| **[!UICONTROL Change Program Status]** | <li>Select program<li>Select new status |
| **[!UICONTROL Remove From List]** | <li>Select Static List <li>Skips person if not currently a member |
| **[!UICONTROL Remove from Marketo List]** | <li>Select a static list in Marketo Engage <li>Skips person if not currently a member |
| **[!UICONTROL Remove Person from Journey]** | <li>Select a live journey <li>Skips person if not currently a member of the target journey |
| **[!UICONTROL Request Marketo Campaign]** | <li>Select a Marketo Engage campaign |
| **[!UICONTROL Send Email]** | <li>Create, edit, or use an AI-personalized email <li>Send-time optimization (optional) |
| **[!UICONTROL Send WhatsApp]** | <li>Select a WhatsApp message |

## Add an action node {#add-an-action-node}

1. Navigate to the journey canvas.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

   ![Click add icon on journey path](./assets/person-journey-canvas-add-node.png){width="200"}

1. In the node properties on the right, select an action from the list and set any values for the action.

+++Activate to destination

Use this action to activate people to Experience Platform destinations directly from your journey. Select the destination and enter an audience name to identify the activated audience in the destination.

![Take an action - Activate to destination](./assets/person-action-node-activate-to-destination.png){width="450"}

+++

+++[!UICONTROL Add Person to Journey]

Use this action to add people to other scheduled or live journeys. People added through this action are immediately added to the audience of the target journey; the journey's audience criteria is not applied.

![Take an action - Add person to journey](./assets/person-action-node-add-to-journey.png){width="450"}

+++

+++[!UICONTROL Add To List]

Use this action to add people to a static list in Journey Optimizer B2B Prime.

![Take an action - Add to list](./assets/person-action-node-add-to-list.png){width="450"}

Choose one of the following options:

* **[!UICONTROL Create]** — Create a new static list asset and add people to it. The list is immediately available for use by other assets in Journey Optimizer B2B Prime.
* **[!UICONTROL Select]** — Selects an existing static list asset where you want to add people who reach the node.

+++

+++[!UICONTROL Add to Marketo List]

Use this action to add people to a static list in Marketo Engage.

![Take an action - Add to Marketo list](./assets/person-action-node-add-to-marketo-list.png){width="450"}

+++

+++[!UICONTROL Change Data Value]

Use this action to update the value of an attribute on a person record. Select the attribute and set the new value.

>[!TIP]
>
>To clear the value of an attribute, set the value to `NULL`.

![Take an action - Change data value](./assets/person-action-node-change-data-value.png){width="450"}

+++

+++[!UICONTROL Change Program Data]

Use this action to update the value of a program attribute. Select the program attribute and set the new value.

![Take an action - Change program data](./assets/person-action-node-change-program-data.png){width="450"}

+++

+++[!UICONTROL Change Program Status]

Use this action to change the status of a person in a Marketo Engage program. Select the program and then select the new status.

![Take an action - Change program status](./assets/person-action-node-change-status-program.png){width="450"}

+++

+++[!UICONTROL Remove From List]

Use this action to remove people from a static list in Journey Optimizer B2B Prime. If a person is not currently a member of the list, the action is skipped for that person.

![Take an action - Remove from list](./assets/person-action-node-remove-from-list.png){width="450"}

+++

+++[!UICONTROL Remove from Marketo List]

Use this action to remove people from a static list in Marketo Engage. If a person is not currently a member of the list, the action is skipped for that person.

![Take an action - Remove from Marketo list](./assets/person-action-node-remove-from-marketo-list.png){width="450"}

+++

+++[!UICONTROL Remove Person from Journey]

Use this action to remove people from other live person journeys. The person is immediately removed from the target journey and no further actions are taken on them. If a person is not currently a member of the target journey, the action is skipped for that person.

![Take an action - Remove person from journey](./assets/person-action-node-remove-from-journey.png){width="450"}

+++

+++[!UICONTROL Request Marketo Campaign]

Use this action to add people to a request campaign in a connected Marketo Engage instance. Select the Marketo Engage campaign to request.

![Take an action - Request Marketo campaign](./assets/person-action-node-request-marketo-campaign.png){width="450"}

+++

+++[!UICONTROL Send Email]

Use this action to send an email to opted-in people. People who are unsubscribed, block listed, email suspended, or marketing suspended skip this action.

![Take an action - Send email](./assets/person-action-node-send-email.png){width="450"}

You can create an email, edit an existing email, or use an AI-personalized email. For information about creating and editing emails, see [Email channel](../marketing/email-channel.md).

You can use [Send-time optimization](../marketing/email-send-time-optimization.md) to personalize email delivery timing by predicting when each profile is most likely to engage.

+++

+++[!UICONTROL Send WhatsApp]

Use this action to send a WhatsApp message. You can create, personalize, and preview WhatsApp messages in the visual design space (see [WhatsApp authoring](../content/whatsapp-authoring.md)).

![Take an action - Send WhatsApp](./assets/person-action-node-send-whatsapp.png){width="450"}

+++
