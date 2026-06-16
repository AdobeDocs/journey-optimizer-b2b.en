---
title: Listen for an Event Node
description: Placeholder
autotag-review: '2026-06-12T23:00:36.531Z'
TQID: 'https://experienceleague.adobe.com/SBEfrrIKSCnO5x1tGXQTz1EZryH0IKhQx4tuqVn78FI'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: d0031543-532c-4a26-8f90-01af2b91e6d0
    internal-label: Event Triggers
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Listen for an event node

Add the _Listen for an event_ node to move your audience forward to the next step in the journey when an event occurs.

## People event filters

| Filters | Description |
| ------- | ----------- |
| Activity history > Email | Email activities based on conditions that are evaluated using one or more selected email messages: <li>Clicked link in email <li>Opened email |
| Activity history > Data Value Changed | For a selected person attribute, a value change occurred. These change types include: <li>New value <li>Previous value <li>Reason <li>Source <li>Date of activity <li> Min. number of times |

## Add an event node

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Listen for an event]**.

1. In the node properties on the right, choose **[!UICONTROL People]** for the event type.

   <!-- ![Journey node - listen to events on people](./assets/node-listen-events-people.png){width="700" zoomable="yes"} -->

1. Select an event from the list.

1. Click **[!UICONTROL Edit event]** and define details for the event.

>[!NOTE]
>
>The timeout functionality for Listen for an event node does not currently function and will be enabled in a later phase.
