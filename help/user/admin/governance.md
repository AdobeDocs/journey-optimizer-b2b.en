---
title: Governance Features
description: Learn about governance features that are currently available in Journey Optimizer B2B Edition.
feature: Setup
role: Admin
exl-id: 2845272b-987c-4a37-adf4-6ee5bfd59fc0
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
    internal-label: Administration
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
autotag-review: 2026-03-27T23:18:44.352Z
TQID: https://experienceleague.adobe.com/PwH34suDPc84nB9eiAWtrkVzsOw82RRGw4hrRogf9zE
---
# Governance features

Journey Optimizer B2B Edition is an integrated Adobe Experience Platform app. It employs several tools and services that provide control of your collected experience data in compliance with your business practices, legal obligations, and development processes. The sections below provide a summary of each of these governance features.

## Privacy - GDPR  

Journey Optimizer B2B Edition uses the existing Marketo Engage GDPR governance features provides by the Privacy Service and Marketo Privacy Broker Service.

## Role-based access control (RBAC)

With Journey Optimizer B2B Edition and access to the Adobe Admin Console, administrators can grant a user permissions on an Entity Type (view-segments, manage-segments, manage-journeys, and so on). This capability is part of the Unified Permissions Framework (UPF) that allows all Adobe Experience Platform customers to define and manage roles and permissions for their organization.

## Data encryption

**_Encryption for data at rest_** - All accounts and person profiles data transferred from Adobe Experience Platform into Journey Optimizer B2B Edition is encrypted to maintain the existing compliance from Experience Platform. All entities originating in Journey Optimizer B2B Edition, such as journeys and buying groups, are also encrypted.

**_Encryption for data in transit_** (over a public network) - All Journey Optimizer B2B Edition APIs and entities are encrypted in transit using TLS 1.2. 

## Consent opt-in/opt-out

Consent opt-in/opt-out is a form of governance where a profile can opt out from a communication channel, such as email or SMS, and a profile is then excluded from the communication channel. 
   
With Journey Optimizer B2B Edition, you can build and manage subscribe/un-subscribe use-cases for your email and SMS delivery use cases. These consent preferences are stored within the XDM Profile Consent Field Group, and are synced into and out of Journey Optimizer B2B Edition as part of the Data Sync Framework. These preferences are used at delivery time to exclude opted out profiles from deliveries.

## Sandbox reset

Sandbox reset is **not currently supported** for Adobe Journey Optimizer B2B Edition. Resetting or deleting a sandbox that is mapped to Journey Optimizer B2B Edition may result in permanent loss of data in Journey Optimizer B2B Edition and could require provisioning of a new Journey Optimizer B2B Edition instance.

## Not yet available

The following governance features are not yet available:

* Data Usage Label Enforcement (DULE) / usage policies
* Data hygiene
* Consent policies
* Field-level access control (FLAC)
* Object-level access control (OLAC)
* CMK encryption for data at rest
* Platform audits service
