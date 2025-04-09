---
title: Adobe Journey Optimizer B2B Edition Overview
description: Discover Adobe Journey Optimizer B2B Edition key features, use cases, and architectures.
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
---
# Adobe Journey Optimizer B2B Edition overview

With Adobe Journey Optimizer B2B Edition, you can orchestrate account and buying group journeys using built-in generative AI and industry-leading automation to maximize demand for specific offerings using marketing-qualified buying groups. 

## Account journeys with buying groups

In comparing Adobe Journey Optimizer B2B Edition to Marketo Engage and Adobe Journey Optimizer standard, the key distinction is that account journeys move accounts through the Journey, not people. A person who is associated with an account typically has a non-linear progression that is based on the progress of the account through the journey, not based on their individual actions. For instance, when an account is in an early phase of the buying journey, the information sent might be about general solution capabilities or features. Further along in the buying process, the content might become more targeted on particular offers or other items geared toward closing a sale. After the solution is purchased, the information might change again to provide how-to guides, best practices, or information about upcoming events, or with content about additional upsells. Even if an individual has not interacted with the early phase content, you still want to progress them to the current phase based not on their own actions, but based on the actions of the other people within their account or buying group. 

## High-level architecture

Adobe Journey Optimizer B2B Edition uses _Account Audiences_ and _People Audiences_ from Adobe Experience Platform to power an account journey, which runs inside of Marketo Engage. Experience Platform is always the source of truth for this data, but all execution and processing of the account journey happens inside of the Marketo Engage B2B marketing infrastructure. The orchestration brings data back to Experience Platform in near real time by the existing Marketo Engage - Adobe Real-Time CDP B2B Edition source connector, which streams data changes from Marketo Engage to Experience Platform.

![High-level data architecture](./assets/high-level-data-architecture.png){width="500" zoomable="yes"}

>[!NOTE]
>
>Check your license entitlements and the corresponding [product description](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} about performance guardrails and static limitations.

### Subscription model

A Journey Optimizer B2B Edition subscription is defined by a pair of Experience Platform (AEP) sandboxes with a Marketo Engage _Munchkin_ subscription. It is not possible for a single Marketo Engage subscription to be paired with more than one AEP sandbox. If you do not choose to pair an existing Marketo Engage subscription with Journey Optimizer B2B Edition, you are provisioned with a new, empty Marketo Engage subscription for use with Journey Optimizer B2B Edition.

The purpose of Experience Platform in this setup is to provide a unified view into the data from the Marketo Engage instances (and any attached CRM systems), and then to be able to action on the unified data using an account journey.

### Account journey operations

Account journeys are authored in Journey Optimizer B2B Edition, and stored in the Marketo Engage instance associated with the subscription. Although it is stored in the Marketo Engage data store, it is not visible from the Marketo Engage UI, and it is only ever usable from Journey Optimizer B2B Edition. 

An account journey always starts with the selection of an account segment to use as the account audience for the journey. The selection of the audience uses the standard Experience Platform audience selector component. Marketers can then implement the account journey by splitting the paths of the journey according to their own criteria, which can include account criteria, people criteria, or buying group criteria. On each branch, actions can be taken to implement the journey, such as sending an email or waiting for an event to occur.

After the account journey is created, it must be published. At publish time, the account journey is validated and converted into a series of Marketo Engage campaigns that implement the journey experience. Data Integration Services are contacted to start the data flow that, in-turn, starts the account journey operations. The first step is to create the segments for the Account's People.

### Data flow

Journey Optimizer B2B Edition uses the Real-Time CDP account segmentation for both defining and executing account segments and related account person segments required by journeys. As a published journey runs, data about the people and accounts can change, and data is collected on the people who interact with the journey. Journey Optimizer B2B Edition relies on the Marketo Engage source connector for Real-Time CDP B2B Edition to flow data changes back to the Experience Platform sandbox, which is the source of truth.  This data is delivered to AEP in a near real-time fashion.   

Only the existing data types supported by the Marketo Engage source connector (accounts, people, and opportunities) flow back into Real-Time CDP. This means that buying group data does not flow to AEP and instead resides in the Marketo Engage instance used by the Journey Optimizer B2B Edition subscription.
