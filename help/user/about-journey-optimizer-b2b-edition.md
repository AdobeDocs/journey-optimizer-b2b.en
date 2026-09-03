---
title: Adobe Journey Optimizer B2B Edition Overview
description: Learn about Adobe Journey Optimizer B2B Edition - orchestrate account journeys with buying groups, AI insights, and Experience Platform integration for B2B marketing.
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
autotag-review: 2026-04-29T23:21:13.339Z
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: f467931a-9b22-4ca8-869f-adfbd64061ce
    internal-label: Onboarding
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
TQID: https://experienceleague.adobe.com/L58cK4MP-S-8U9fFiXU2qZn4HCieNzjoOaSRCLkyanI
---
# Adobe Journey Optimizer B2B Edition overview

With Adobe Journey Optimizer B2B Edition, you can orchestrate person and account journeys using built-in generative AI and industry-leading automation to maximize demand for specific offerings using marketing-qualified buying groups. 

## Account journeys with buying groups

When comparing account journeys to the journey capabilities in Marketo Engage and Adobe Journey Optimizer standard, the key distinction is that account journeys move accounts through the journey, not people. A person who is associated with an account typically has a non-linear progression that is based on the progress of the account through the journey, not based on their individual actions. For instance, when an account is in an early phase of the buying journey, the information sent is typically about general solution capabilities or features. Further along in the buying process, the content becomes more targeted on particular offers or other items geared toward closing a sale. After the solution is purchased, the information changes again to provide how-to guides, best practices, information about upcoming events, or content about additional upsells. Even if an individual has not interacted with early phase content, you can progress them to the current phase based on the actions of others within their account or buying group. 

## High-level architecture

Adobe Journey Optimizer B2B Edition is built on Adobe Experience Platform, including Real-Time CDP B2B. Journey Optimizer B2B Edition and Marketo Engage run on separate systems, each with its own data store. Experience Platform is the primary data store and authoritative source for accounts, people, and opportunities. Journey Optimizer B2B Edition owns your account journeys, buying groups, and buying group roles.

A dedicated Marketo Engage instance supports each Journey Optimizer B2B Edition subscription. This instance does not store your account journeys, audiences, or buying groups. Instead, it provides entitlements and backend services, such as email delivery, sender configuration, and branding domains.

To support journey actions, you can also connect one or more of your existing Marketo Engage instances, including your production instance. Journey actions let marketers coordinate account-based journeys in Journey Optimizer B2B Edition with lead-based campaigns in Marketo Engage, such as adding people to a list or a request campaign. [Learn more about connecting Marketo Engage instances](./admin/marketo-actions-connect.md).

![High-level data architecture showing Journey Optimizer B2B Edition connected to Adobe Experience Platform as the source of truth for account and people audiences, a dedicated Marketo Engage instance that provides entitlements and backend services, and an optional production Marketo Engage instance used to run journey actions.](./assets/high-level-data-architecture.png){zoomable="yes"}

>[!NOTE]
>
>Check your license entitlements and the corresponding [product description](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} for performance guardrails and static limitations.

### Subscription model

An Experience Platform sandbox paired with a dedicated Marketo Engage instance defines a Journey Optimizer B2B Edition subscription. This dedicated instance is separate from your production Marketo Engage instance, and it exists to support entitlements and backend services rather than to store account journey data. [Learn more about setup](./setup-ultimate.md).

Experience Platform provides a unified view of data from your connected Marketo Engage instances and CRM systems. Use that unified data to build and run your journeys.

### Journey operations

Journey Optimizer B2B Edition creates, stores, and runs your account journeys. Account journeys do not appear in Marketo Engage, and they are only usable in Journey Optimizer B2B Edition.

A journey always starts with an audience that qualifies leads or accounts and their people for the journey. Select this audience using the standard Experience Platform audience selector. Marketers implement the journey by splitting paths using account criteria, people criteria, or buying group criteria. On each path, actions send communications or wait for an event to occur.

After you create an account journey, publish it to make the journey live. Qualifying accounts enter a published journey within 24 hours.

### Data flow

Journey Optimizer B2B Edition functions as an Adobe Real-Time CDP B2B Edition destination. Use Real-Time CDP account segmentation to build and evaluate the account audiences and people audiences that qualify accounts and people for a journey. When you publish a journey, Journey Optimizer B2B Edition activates the qualifying audiences from Experience Platform.

Buying groups, buying group roles, and buying group scores are created and stored in Journey Optimizer B2B Edition. [Learn more about buying groups](./buying-groups/buying-groups-overview.md).
