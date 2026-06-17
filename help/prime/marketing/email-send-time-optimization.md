---
title: Email Send-Time Optimization
description: Send-time optimization (STO) in Adobe Journey Optimizer B2B Prime personalizes email delivery for person journeys. Learn how to enable STO and improve engagement.
autotag-review: '2026-06-17T20:52:02.535Z'
TQID: 'https://experienceleague.adobe.com/wlxhS7E8DnbThm5ge-wzTkMcn-eBzFUXfw3ZGrfcRHA'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
    internal-label: Email channel
---
# Email send-time optimization

Use the Send-time optimization (STO) feature to personalize email delivery timing for [person journeys](./person-journeys.md) by predicting when each profile is most likely to engage. Instead of a fixed send time, STO uses historical email engagement signals to schedule delivery at the optimal time for each recipient, improving overall engagement.

STO analyzes each profile's historical engagement using a large language model. It predicts and ranks potential send times, then schedules delivery at the highest-ranked time within the optimization window.

<!-- Performance insights, such as usage, engagement lift, and STO vs. non-STO comparisons, are available through natural language queries in the AI Assistant. -->

>[!BEGINSHADEBOX]

There are many **_future enhancements_** planned for STO:

* Global STO configuration in the _[!UICONTROL Admin]_ area
* Journey-level STO enablement
* Configurable test / control splits

>[!ENDSHADEBOX]

## Configuration {#configuration}

You can configure send-time optimization when you [add a _[!UICONTROL Take an action]_ node](./action-nodes.md) to a person journey and choose the **[!UICONTROL Send email]** action.

1. Select the _Send email_ journey action node.

1. In the node properties on the right, enable the **[!UICONTROL Send-time Optimization]** option.

   ![Send email journey node - Send-time Optimization options](./assets/email-node-send-time-optimization.png){width="450" zoomable="no"}

1. To specify the window and test distribution, set the STO options:

   * **[!UICONTROL Send within next]** - This value determines the optimization window (in days), which is the time range in which emails can be delivered. For example, for a webinar occurring in five days, you might set a four- or five-day window. STO selects the best predicted send time for each profile within this window.

   * **STO / Fixed distribution** - STO automatically creates a _test and control split_ to divide eligible profiles between optimized and fixed send times. The split enables direct performance comparison. (Future enhancements are planned to allow custom split percentages.)

   >[!NOTE]
   >
   >Profiles with strong engagement history are split evenly into control and test groups to measure STO impact. To ensure statistically reliable results, the STO vs. non‑STO split is constrained between 30% and 70%. This helps prevent smaller cohorts from skewing outcomes and ensures meaningful comparisons.

1. Directly after the _[!UICONTROL Send email]_ node, [add a _Wait_ node](./wait-nodes.md).

   A wait node must immediately follow an STO-enabled email action. Adding this node ensures that profiles remain in the journey until the full optimization window is cleared and all STO sends are complete. If you omit this node, the system flags the configuration as invalid.

1. After you complete the rest of the person journey, proceed to [publish](./person-journeys.md#publish).

## Reporting


