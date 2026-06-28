---
title: Person Journey Nodes
description: Learn about person journey nodes in Journey Optimizer B2B Edition Prime - audience, actions, events, waits, path splits, and AI-driven next best path routing.
autotag-review: '2026-06-16T21:21:16.531Z'
TQID: 'https://experienceleague.adobe.com/sTnrOvrGIrgboPqOMrrkUvNU1y6zZJX42zEJxuUInKQ'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Person journey nodes

After you create a [person journey](./person-journeys.md), use the tools in the canvas to add the audience and build out the journey using nodes. The journey canvas provides a visual design space, where you can build your multistep B2B marketing use cases.

The _[!UICONTROL Person audience]_ node is automatically the first node in the journey. After you select the audience, build your journey by combining the different action, event, and decisioning nodes as a multistep, cross-channel scenario. Each node of a journey represents a step along a logical path.

:::: landing-cards-container

:::
<!-- ![Person audience node](https://cdn.experienceleague.adobe.com/icons/users.svg) -->

Person audience node

The journey always starts with a person audience node. Set the input audience using a static or dynamic people list to define which person profiles enter the journey.

[Learn about the person audience node](./person-audience-node.md)
:::

:::
<!-- ![Action nodes](https://cdn.experienceleague.adobe.com/icons/circle-play.svg) -->

Action nodes

Apply changes to every person on a path, such as sending an email or updating a data value attribute.

[Learn about action nodes](./action-nodes.md)
:::

:::
<!-- ![Event nodes](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg) -->

Event nodes

Advance people to the next journey step when a specific activity or data change occurs, such as opening an email or a data value change.

[Learn about event nodes](./listen-for-event-nodes.md)
:::

:::
<!-- ![Wait nodes](https://cdn.experienceleague.adobe.com/icons/clock.svg) -->

Wait nodes

Pause journey progression for a set duration or until a specific date and time before moving people to the next step.

[Learn about wait nodes](./wait-nodes.md)
:::

:::
<!-- ![Split and merge paths nodes](https://cdn.experienceleague.adobe.com/icons/code-branch.svg) -->

Split and merge paths nodes

Segment people into separate paths based on conditions, apply different actions or events per path, then merge the paths to continue the journey.

[Learn about split and merge paths nodes](./split-merge-paths-nodes.md)
:::

:::
<!-- ![Next best path node](https://cdn.experienceleague.adobe.com/icons/lightbulb.svg) -->

Next best path node

Use AI-driven decisioning to route each person to the most relevant path. Describe your intent in natural language and let the system evaluate profile context, engagement history, and account data to make the routing decision.

[Learn about the next best path node](./next-best-path.md)
:::

::::
