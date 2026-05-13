---
title: Test Email Rendering
description: Test email rendering across desktop, mobile, and web clients with Litmus integration to ensure inbox compatibility in Journey Optimizer B2B Edition.
feature: Email Authoring, Integrations
level: Intermediate
role: User
exl-id: 26d87a56-6bd1-4d4a-8090-71f5b0a7e9f8
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
    internal-label: Content management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: cad51180-f8ce-4cb7-aefc-437847b5d6d6
    internal-label: Cross channel delivery
autotag-review: 2026-03-30T22:28:13.343Z
TQID: https://experienceleague.adobe.com/G9c2TdbEje4HgE82tKURAn-UYz5wB-9iLsT9805m1JI
---
# Test email rendering with Litmus

To test your emails, you can leverage a [Litmus](https://www.litmus.com/email-testing){target="_blank"} Enterprise account from Journey Optimizer B2B Edition. With this integration, you can preview your email rendering in popular email clients. This tool helps you to ensure that your email content looks great and works as designed in every inbox.

>[!AVAILABILITY]
>
>This integration is only available for Journey Optimizer B2B Edition users with Litmus Enterprise accounts. For more information, refer to the [solution page on the Litmus website](https://www.litmus.com/solutions/esp/adobe-journey-optimizer){target="_blank"}.

1. When your email design is complete and ready to be tested, click **[!UICONTROL Simulate content]** in the email design space.

1. Click **[!UICONTROL Render email]** at the top right.

   ![Render email button](./assets/email-simulate-render-button.png){width="700" zoomable="yes"}

   If you have not yet connected to your Litmus account from Journey Optimizer B2B Edition, the displayed page provides an option for starting a trial account or connecting to your existing account.

1. Click **[!UICONTROL Connect your Litmus account]** on the top right, or use the link inside the page.

   ![Connect your Litmus account](./assets/email-simulate-render-litmus-connect.png){width="700" zoomable="yes"}

1. Enter your Litmus account credentials and click **[!UICONTROL Sign in]**.

1. Click **[!UICONTROL Connect]** to confirm the connection between Litmus and Journey Optimizer B2B Edition and send the email content for rendering.

   >[!IMPORTANT]
   >
   >When you connect your Litmus account with Journey Optimizer B2B Edition, you agree that test messages are sent to Litmus. This content is then managed within Litmus and not Adobe. As a consequence, the Litmus data retention email policy applies to these emails, including personalization data that may be included in the test messages.

1. Click **[!UICONTROL Run test]** at the top right to generate email previews.

   ![Run a Litmus rendering test](./assets/email-simulate-render-litmus-run-test.png){width="700" zoomable="yes"}

1. Check your email content in popular desktop, mobile and web-based clients.

   Click the displayed thumbnail to view the details for any of the rendered client tests.

   ![Litmus email previews](./assets/email-simulate-render-litmus-previews.png){width="700" zoomable="yes"}

1. When you are finished reviewing, click the back arrow ( ![Show or hide filters icon](../../assets/do-not-localize/icon_back-arrow.svg) ) at the top-left to return to the Simulate content page. 

   You can select another profile and do another rendering test, or return to the email design space to make any needed adjustments based on your review.
