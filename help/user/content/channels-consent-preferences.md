---
title: Channel Messaging Consent
description: Learn how Journey Optimizer B2B Edition reads AEP XDM profile consent preferences and enforces opt-in and opt-out at message delivery time for email, SMS, and WhatsApp channels.
feature: Setup, Channels
role: Admin, User
autotag-review: '2026-05-19T16:18:37.228Z'
TQID: 'https://experienceleague.adobe.com/-c0dJnpfiIcj0B5gViyEQ7E1Ws0BwP864OLF003rOjw'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
subfeature_v2:
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
    internal-label: Email channel
  - id: a22f05f6-0fcf-40c0-a70e-e13a3db185f7
    internal-label: SMS channel
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Channel messaging consent

Adobe Journey Optimizer B2B Edition reads per-person consent preferences stored in Adobe Experience Platform XDM profiles and enforces them at message delivery time, as part of the app's [governance controls](../admin/governance.md). Persons who opted out of a channel are excluded from delivery before content is sent from the channel or downstream messaging provider.

The following sections describe how Journey Optimizer B2B Edition evaluates consent at message send time for each supported channel.

## Email {#email}

Journey Optimizer B2B Edition evaluates the following XDM attribute for email consent when sending messages on the [email channel](../admin/configure-channels-emails.md):

| XDM attribute | `y` | `n` | No value |
| --- | --- | --- | --- |
| `consents.marketing.email.val` | Opted in | Opted out | Opted in |

Keep the following considerations in mind for email consent:

* Persons who opted out globally from email can receive emails marked as operational.
* Subscription-level preferences are not supported.

## SMS {#sms}

Journey Optimizer B2B Edition evaluates the following XDM attributes for SMS consent when sending messages through the [SMS channel](../admin/configure-channels-sms.md):

| XDM attribute | `y` | `n` | No value |
| --- | --- | --- | --- |
| `consents.marketing.sms.val` | Opted in | Opted out | Opted out |
| `consents.marketing.subscriptions.<senderID>` | Opted in | Opted out | Opted out |
| `consents.marketing.sms.subscriptions.<senderId>.subscribers.<phoneNumber>` | Opted in | Opted out | Opted out |

Keep the following considerations in mind for SMS consent:

* When a lead (person) record is opted out of SMS, the record is excluded entirely and is not passed to downstream SMS providers.
* When available, subscription-level consent is evaluated. Global opt-out is used as a fallback when subscription-level consent is unavailable.
* Persons opted out from SMS can still receive messages marked as operational.
* If multiple lead records share the same phone number, they share the same opt-in or opt-out status.

## WhatsApp {#whatsapp}

Journey Optimizer B2B Edition evaluates the following XDM attributes for WhatsApp consent when sending messages through a configured [WhatsApp channel](../admin/configure-channels-whatsapp.md):

| XDM attribute | `y` | `n` | No value |
| --- | --- | --- | --- |
| `consents.marketing.whatsApp.val` | Opted in | Opted out | Opted out |
| `consents.idSpecific.Phone.<number>.marketing.whatsApp.val` | Opted in | Opted out | Opted out |

Keep the following considerations in mind for WhatsApp consent:

* If the global WhatsApp attribute value (`consents.marketing.whatsApp.val`) is present, it is used for consent evaluation.
* If the global attribute value is not present but a sender-specific entry is present, the sender-specific entry is used for consent evaluation.
* If no value is present for either attribute, the person is treated as opted out.

## Not supported {#not-supported}

The following consent-related features are not currently supported in Journey Optimizer B2B Edition:

* AEP Consent Policies
* Marketing Preferred attributes (`consents.marketing.preferred`)
