---
title: Email Deduplication
description: Learn how to use email deduplication in account journeys to prevent the same email from being sent multiple times to the same email address.
feature: Account Journeys, Email
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: email, deduplication, journey, duplicate
---
# Email deduplication

Use email deduplication in account journeys to ensure that the same email is not sent multiple times to the same email address within a journey. When you enable this feature, duplicate email addresses are blocked until the first record with that email address completes the journey. After an account finishes a journey, a person can qualify to receive emails again as part of a new account entering the journey.

## When to use email deduplication

There are a couple of key scenarios where you should consider enabling email deduplication:

* **Email is not used as an identity in Real-Time CDP** - The same email address may appear across multiple person profiles. If those duplicate profiles qualify for the same journey and you want to prevent sending the email more than once, enable this feature.

* **Single person associated with multiple accounts** - If your Real-Time CDP data model allows a single person to be associated with multiple accounts, and you want to avoid sending the same email twice to that person when multiple accounts (including profiles with the same email address) qualify for the same journey, enable this feature.

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

When email deduplication is enabled, the journey checks each email address before sending the email. If a record with the same email address already entered that journey node, the new entry is blocked until the first record completes the journey.
