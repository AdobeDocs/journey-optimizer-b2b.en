---
title: Person Audience Journey Node
description: Placeholder page for person journeys.
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

