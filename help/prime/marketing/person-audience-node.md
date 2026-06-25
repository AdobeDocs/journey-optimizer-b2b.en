---
title: Person Audience Journey Node
description: Configure the person audience node in Journey Optimizer B2B to specify which profiles enter a journey using dynamic people lists or event-based audiences.
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
autotag-review: '2026-06-16T21:21:01.614Z'
TQID: 'https://experienceleague.adobe.com/pk1NGg3M67oRieuCOZFdaguKl2bVkiZyEPVnJDTUBJs'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Person audience node

The _person audience_ node specifies which person profiles enter the journey. When you [create a person journey](./person-journeys.md), the journey always starts with a person audience node that defines its input. The person audience node can have one of two audience input types: a static people list or a dynamic people list.

If the dynamic people list that you need for the person journey does not aleady exist, [create the people list](../audiences/people-lists.md#create-a-people-list) and then configure the Person audience node.

_To configure the journey audience:_

1. Click the **[!UICONTROL Person audience]** node.

   This action displays the node properties on the right.

   ![Person audience journey node](./assets/person-audience-node-properties.png){width="500" zoomable="yes"}

1. Use one of the following audience configuration options for the person audience:

   * **[!UICONTROL Dynamic list]** - Use a dynamic, rules-based people list. The list rules are evaluated at journey runtime to qualify members of the journey. People that later disqualify for the dynamic list are not removed from the journey. See _[Dynamic lists](../audiences/people-lists.md#dynamic-lists)_.

   * **[!UICONTROL Event audience]** - Use an event audience define the journey audience based on qualifying events. Define audience members using person profile filtering and trigger journey entry using event criteria. See _[Event-based audiences](../audiences/event-based-audiences.md)_.
