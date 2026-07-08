---
title: Governance and Privacy Features
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
# Governance and privacy features

[!DNL Journey Optimizer B2B Edition] is an integrated Adobe Experience Platform app. It employs several tools and services that provide control of your collected experience data in compliance with your business practices, legal obligations, and development processes. The sections below provide a summary of each of these governance features.

## Privacy

There are various regulations that apply to [!DNL Journey Optimizer B2B Edition] customers who hold data for Data Subjects residing in the respective regions or countries mentioned above (EU, California, Thailand, Brazil, New Zealand). This information on this page is not legal advice and does not warrant your compliance with applicable law.

### GDPR

General Data Protection Regulation (GDPR) is the European Union's (EU) privacy law that harmonizes and modernizes [data protection requirements](https://commission.europa.eu/law/law-topic/data-protection/data-protection-explained_en){target="_blank"} for EU countries.

[!DNL Journey Optimizer B2B Edition] uses the existing Marketo Engage GDPR governance features provided by the Privacy Service and Marketo Privacy Broker Service.

### CNIL

On April 14, 2026, the Commission nationale de l'informatique et des libertés (CNIL) [published a recommendation](https://cnil.fr/sites/default/files/2026-05/recommandation_tracking_pixels_emails.pdf) on the use of tracking pixels within emails. The guidance clarifies when consent is required and highlights the importance of proper consent practices for email pixel tracking. This policy impacts any entity sending emails to subscribers based in France.

CNIL provided a three-month period from the date of the recommendation for companies to inform their email recipients of the presence of the tracking pixels, their purpose, and the recipients' right to opt-out. During this transition period, Marketo Engage users are expected to notify their recipients about pixel tracking and provide an opt-out if necessary. CNIL is expected to begin enforcement activities after July 14, 2026.

As the CNIL and other regulators clarify guidance on tracking pixels and related issues, Adobe will continue to monitor updates and inform you of changing technical capabilities.

[!DNL Journey Optimizer B2B Edition] offers controls that help you manage open tracking at the email level. Users are responsible for determining their own compliance obligations under applicable CNIL guidance and other laws. For infromation about using these capabilities to manage email open tracking, see [_Manage email tracking_](../content/email-tracking-manage.md).

## Role-based access control (RBAC)

With Journey Optimizer B2B Edition and access to the Adobe Admin Console, administrators can grant a user permissions on an Entity Type (view-segments, manage-segments, manage-journeys, and so on). This capability is part of the Unified Permissions Framework (UPF) that allows all Adobe Experience Platform customers to define and manage roles and permissions for their organization.

## Data encryption

**_Encryption for data at rest_** - All account and person profile data transferred from Adobe Experience Platform into Journey Optimizer B2B Edition are encrypted to maintain the existing compliance from Experience Platform. All entities originating in Journey Optimizer B2B Edition, such as journeys and buying groups, are also encrypted.

**_Encryption for data in transit_** (over a public network) - All Journey Optimizer B2B Edition APIs and entities are encrypted in transit using TLS 1.2. 

## Consent opt-in/opt-out

Journey Optimizer B2B Edition reads per-person consent preferences stored in Adobe Experience Platform XDM profiles and enforces them at message delivery time for email, SMS, and WhatsApp channels. A person who opted out of a channel is excluded from delivery before content is sent from the channel or downstream messaging provider.

Consent is evaluated at the time of delivery using XDM fields from the Profile Consent Field Group. The default consent behavior differs by channel — email defaults to opted in when no preference is set, while SMS and WhatsApp default to opted out.

For details on the XDM attributes evaluated for each channel and their default behaviors, see [Consent preferences](../content/channels-consent-preferences.md).

## Sandbox reset

Sandbox reset is **not currently supported** for Adobe Journey Optimizer B2B Edition. Resetting or deleting a sandbox mapped to Journey Optimizer B2B Edition may cause permanent data loss and require provisioning a new instance.

## Not yet available

The following governance features are not yet available:

* Data Usage Label Enforcement (DULE) / usage policies
* Data hygiene
* Consent policies
* Field-level access control (FLAC)
* Object-level access control (OLAC)
* CMK encryption for data at rest
* Platform audits service
