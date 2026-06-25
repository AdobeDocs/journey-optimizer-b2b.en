---
title: Event-based Audiences
description: Use event-based audiences in Journey Optimizer B2B Prime to trigger person journey entry in near real time based on Marketo Engage activities.
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
autotag-review: '2026-06-25T17:59:01.953Z'
TQID: 'https://experienceleague.adobe.com/04J58rjKw0hCoTOeYheZIPaX-YR8GwP-k6-Wn3XCetU'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Event-based audiences

In [!DNL Adobe Journey Optimizer B2B Prime], _event‑based audiences_ let you add audience members to a live [person journey](../marketing/person-journeys.md) in near real time when a [!DNL Marketo Engage] activity occurs. You configure event‑based audiences on the Audience node of the journey canvas:

* Select one or more Marketo activities (standard or custom) as the qualifying events.
* Optionally add person profile filters (such as industry, region, or lifecycle stage) to narrow which people can enter.
* Optionally define activity‑attribute constraints (such as a specific form, URL, or program) to narrow which occurrences of each activity qualify.

When a qualifying activity is logged in [!DNL Marketo Engage] for a lead and replicated into [!DNL Adobe Journey Optimizer B2B Prime], the system evaluates the corresponding person record against your configured filters and constraints. If the conditions are met, the person enters the journey immediately through the Audience node.

_To define an event-based audience for a person journey:_

1. Select the [_Person audience_ node](../marketing/person-audience-node.md).

1. In the node properties on the right, choose **[!UICONTROL Event audience]** as the entry type.

    ![Person audience journey node set to event-based audience](./assets/event-based-audience-node.png){width="400"}

1. Click **[!UICONTROL Add event criteria]**.

1. In the _[!UICONTROL Edit event criteria]_ dialog, add one or more [!DNL Marketo Engage] activities as qualifying events, such as:

   * _Attends webinar_
   * _Email is delivered_
   * _Clicks link in email_

   >[!NOTE]
   >
   >You can also select custom activities defined in the associated [!DNL Marketo Engage] instance.

   Set the matching operator and values for each activity.

   ![Activity triggers for an event-based audience](./assets/event-based-audience-triggers.png){width="700" zoomable="yes"}

   A person qualifies for the journey when any one of those configured activities is logged for that lead.

1. (Optional) To use an event and filter combination for audience qualification, add person‑level filters.

   * Select the **[!UICONTROL Filters]** tab.
   * Drag each filter and set the matching criteria.

   ![Person filters for an event-based audience](./assets/event-based-audience-filters.png){width="700" zoomable="yes"}   

   If you add filters, the person must satisfy at least one configured activity condition and the configured filters.

1. Click **[!UICONTROL Save]**.
