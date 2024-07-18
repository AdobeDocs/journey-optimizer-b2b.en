---
title: Adobe Journey Optimizer B2B Edition overview
description: Discover Adobe Journey Optimizer B2B Edition key features, use cases, and architectures.
---
# Adobe Journey Optimizer B2B Edition overview

With Adobe Journey Optimizer B2B Edition, you can orchestrate account and buying group journeys using built-in generative AI and industry-leading automation to maximize demand for specific offerings using marketing-qualified buying groups.

## Account journeys with buying groups

In comparing Adobe Journey Optimizer B2B Edition to Marketo Engage and Adobe Journey Optimizer standard, the key distinction is that account journeys move accounts through the Journey, not people. A person who is associated with an account most likely has a non-linear progression, based on the progress of the account through the journey, not based on their individual actions. For instance, when an account is in an early phase of the buying journey, the information sent might be about general solution capabilities or features. Further along in the buying process, the content might become more targeted on particular offers or other items geared toward closing a sale. After the solution is purchased, the information might change again to provide how-to guides, best practices, or information about upcoming events, or with content about additional upsells. Even if an individual has not interacted with the early phase content, you still want to progress them to the current phase based not on their own actions, but based on the actions of the other people within their account or buying group. 

## High-level architecture

Adobe Journey Optimizer B2B Edition uses _Account Audiences_ and account's _People Audiences_ from Adobe Experience Platform to power an account journey, which is run inside of Marketo Engage. Experience Platform is always the source of truth for this data, but all execution and processing of the account journey happens inside of the Marketo Engage B2B marketing infrastructure. The orchestration brings data back to Experience Platform in near real time by the existing Marketo Engage - Adobe Real-Time CDP B2B Edition source connector, which streams data changes from Marketo Engage to Experience Platform.

![High-level data architecture](./assets/high-level-data-architecture.png){width="600" zoomable="yes"}

### Subscription model

A Journey Optimizer B2B Edition subscription is defined by a pair of an Experience Platform (AEP) sandboxes with a Marketo Engage _munchkin_ subscription. It is not possible for a single Marketo Engage subscription to be paired with more than one AEP sandbox. If you don't choose to use an existing Marketo Engage subscription with Journey Optimizer B2B Edition, or you do not currently use Marketo Engage, you are provisioned with a new, empty Marketo Engage subscription for use with Journey Optimizer B2B Edition.
