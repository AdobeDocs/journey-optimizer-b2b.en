---
title: Email Deduplication
description: Learn how to use email deduplication in account journeys to prevent the same email from being sent multiple times to the same email address.
feature: Account Journeys, Channels
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: email, deduplication, journey, duplicate
exl-id: 93107acd-1cb2-4316-acfc-e32ab1e065ae
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
autotag-review: 2026-03-30T22:08:16.582Z
TQID: https://experienceleague.adobe.com/aWKXaC6x4Izeh81A6Fpy-Nrf18fHgnq6jUc-82ohErs
---
# Email deduplication

To ensure that the same email is not sent multiple times to the same email address within a journey, use email deduplication in account journeys. When you enable this feature, duplicate email addresses are blocked until the first record with that email address completes the journey. After an account finishes a journey, a person can qualify to receive emails again as part of a new account entering the journey.

## When to use email deduplication

There are some key scenarios to consider for enabling email deduplication:

* **Email is not used as an identity in Real-Time CDP** - The same email address may appear across multiple person profiles. If those duplicate profiles qualify for the same journey and you want to prevent sending the email more than once, enable this feature.

* **Single person associated with multiple accounts** - If your [!DNL Real-Time CDP] data model associates a single person with multiple accounts, enable this feature to avoid sending the same email twice when multiple profiles with the same email address qualify for the same journey.

>[!NOTE]
>
>Email deduplication applies at the journey level. If a person with the same email address qualifies for different journeys, they can still receive emails from each journey.

## Enable email deduplication for a journey

To enable email deduplication for an account journey:

1. Open an account journey.

1. Click **[!UICONTROL More]** (**...**) in the top-right corner of the journey workspace.

   ![Journey workspace with More menu expanded showing Email Deduplication option](./assets/email-deduplication-more-menu.png){width="450"}

1. Choose **[!UICONTROL Email Deduplication]**.

1. In the dialog, select the **[!UICONTROL Email Deduplication]** checkbox.

   ![Email Deduplication dialog with toggle enabled](./assets/email-deduplication-dialog.png){width="400"}

1. Click **[!UICONTROL Save]**.

When email deduplication is enabled, the journey checks each email address before sending the email. If a record with the same email address has already entered that journey node, the new entry is blocked until the first record completes the journey.
