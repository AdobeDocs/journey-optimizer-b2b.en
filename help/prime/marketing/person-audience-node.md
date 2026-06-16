---
title: Person Audience Journey Node
description: Placeholder page for person journeys.
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

If the people list that you need for the person journey does not aleady exist, [create the people list](../audiences/audience-management.md#create-a-people-list) and then configure the Peson audience node.

## Set the audience for the person audience node

1. Click the **[!UICONTROL Person audience]** node.

   This action displays the node properties on the right.

   <!-- ![Person audience journey node](./assets/person-journey-person-audience-node.png){width="700" zoomable="yes"} -->

1. In the node properties panel on the right, use one of the following input options for the person audience journey node:

   * **[!UICONTROL Dynamic list]** - Use a dynamic, rules-based people list. The list rules are evaluated at journey runtime to qualify members of the journey. People that later disqualify for the dynamic list are not removed from the journey.

   * **[!UICONTROL Static list]** - Use a static list of people as member of your journey. The current list membership is evaluated at journey runtime to qualify members for the journey. People that are later removed from the static list are not removed from the journey.

