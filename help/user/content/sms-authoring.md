---
title: SMS Authoring
description: Learn how to send text messages (SMS) to your customers on their mobile devices, and to personalize and preview messages in text format from the SMS editor.
feature: SMS Authoring, Content, Channels
role: User
exl-id: bd648253-74de-4083-a37a-ab7ceaea2746
---
# SMS authoring

Use Adobe Journey Optimizer B2B Edition to send text messages (SMS) to your customers on their mobile devices. You can create, personalize, and preview messages in text format from the SMS editor.

Before creating SMS messages for account journeys, make sure that the [SMS service provider is configured](../admin/configure-channels-sms.md) from the _[!UICONTROL Administrator]_ settings.

## Add an SMS action in an account journey

You can set up text message deliveries in an account journey when you add a _[!UICONTROL Take an action]_ node and do the following:

1. For the _[!UICONTROL Action on]_ target, choose **[!UICONTROL People]**.

1. For the _[!UICONTROL Action on people]_, choose **[!UICONTROL Send SMS]**.

   ![Take an action - send sms](assets/journey-node-send-sms.png){width="800" zoomable="yes"}

1. At the bottom of the _[!UICONTROL Take an action]_ panel, click **[!UICONTROL Create SMS]**.

1. In the dialog, enter a unique **[!UICONTROL Name]** for the SMS message.

   ![Create new SMS dialog](assets/create-new-sms.png){width="400"}

1. Click **[!UICONTROL Create]**.

   The _Journey map_ opens and you can create the message and set the SMS properties for sending the message.

### Create the SMS message

>[!IMPORTANT]
>
>**SMS consent management**<br/>
>
>In accordance with the industry standards and regulations, all SMS marketing messages must contain a way for the recipients to unsubscribe easily. To do this, SMS recipients can reply with opt-in and opt-out keywords. All standard opt-in and opt-out keywords are supported and honored. In addition, any custom keywords configured for your SMS service provider account are supported and honored.

Enter the text that you want to send in the **[!UICONTROL Message]** field.

You can create a message of up to 1600 characters, with every 160 characters considered as a single SMS message.

![Click the Personalize icon to add tokens to the message](./assets/sms-message-compose.png){width="800" zoomable="yes"}

#### Personalize the text message

1. At anytime while authoring the text message, click the _Personalize_ icon ( ![Personalize icon](../assets/do-not-localize/icon-personalize.svg) ) to the right of the text message box.
   
   The displayed page provides access to your Adobe Marketo Engage Lead and System tokens. Both standard and custom tokens are included. You can use the _Search_ bar to locate the token you need, or navigate through the folder tree to find and select any of the lead/system tokens.

1. Place your cursor at the location in the message where you want to add the token.

1. Add a token by clicking the plus ( **+** ) symbol next to it.

   If you want to add the token with a fallback (default that appears in case that field is not available for a lead), click the _More_ icon ( **...** ) and choose **[!UICONTROL Insert with fallback text]**.

   ![Click the ellipses to use a fallback for the token](./assets/sms-message-personalize-ellipsis-fallback.png){width="700" zoomable="yes"}

1. In the _[!UICONTROL Enter fallback value]_ dialog, enter the text that appears as a fallback and then click **[!UICONTROL Add]**.

   ![Enter the fallback text for the token](./assets/sms-message-personalize-fallback-text.png){width="400"}

1. When your personalization tokens are placed, click **[!UICONTROL Save]** to save changes and return to the main SMS authoring workspace.

   You can continue to edit the message with the tokens as needed. 

#### Add links (URLs) to the text message

1. After entering your message text, click the _Link_ icon ( ![Link icon](../assets/do-not-localize/icon-link.svg) ) to the right of the text message box.
   
1. In the dialog, choose the type of URLs to link:

   * **[!UICONTROL Landing Page]** - Choose this option to select any of the approved Adobe Marketo Engage landing pages from your Marketo Engage instance. Select the workspace, and then select the landing page.

   * **[!UICONTROL External URL]** - This type is any external URL that you enter in the text box.

1. If you choose to use a landing page, set the tracking options.

   * **[!UICONTROL Enable tracking]** - Select this checkbox to enable tracking, which requires _shortening_ the URL. For a landing page, it uses the Marketo Engage subdomain for the shortened URL. A sample of the shortened URL format is displayed. The actual URL is created when the SMS is sent to the recipient.

   * **[!UICONTROL Include mkt_tok]** - Select this checkbox to track activity against a user.

      >[!NOTE] 
      >
      >When you allow tracking but disable _[!UICONTROL Include mkt_tok]_, the destination URL does not include the `mkt_tok` query string parameter after redirect. This parameter is used by Marketo Engage landing pages and Munchkin to ensure that tracking of person activities (such as when a person unsubscribes from an email). Do not disable this option unless the parameter is causing issues on your website.<br/>
      >For more information about using Munchkin tracking codes on your website, refer to the [Marketo Engage documentation](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/additional-integrations/add-munchkin-tracking-code-to-your-website){target="_blank"}.

   ![Add link dialog for SMS message](./assets/sms-add-link-dialog.png){width="470"}
  
1. When the link options are complete, click **[!UICONTROL Add]** to save the changes and add the URL link to the SMS message.

### Set the SMS properties

1. In the _[!UICONTROL SMS properties]_ section, enter a **[!UICONTROL Name]** (required, 100 character maximum) and **[!UICONTROL Description]** (optional, 300 character maximum) for your message. 

   Alpha, numeric, special characters are allowed for these fields. The following reserved characters are **not allowed**: `\`, `/`, `:`, `*`, `?`, `"`, `<`, `>` and `|`.

1. Choose the **[!UICONTROL SMS Type]**:

   * Use `Marketing` for promotional text messages, which require user consent.
   * Use `Transactional` for non-commercial messages, such as order confirmation, password reset notifications, or delivery information.

1. For **[!UICONTROL SMS configuration]**, choose one of the pre-defined API configurations.

   This setting determines which SMS gateway service provider and account is used to deliver the message.

1. Enter the **[!UICONTROL Sender number]** ​that you want to use for your communications.

   ![Take an action - send sms](./assets/sms-properties.png){width="700" zoomable="yes"}

   The recipient number is always mapped to the `Lead.mobilePhone` field in Marketo Engage.

### Simulate the text message content {#preview-test}

>[!CONTEXTUALHELP]
>id="ajo-b2b_sms_preview_simulate"
>title="Check how your content is rendering"
>abstract="When your content is defined, you can preview it and check the rendering for the channel that you are using."

When your message content is defined, you can use test profiles to simulate (preview) its content. If you inserted personalized content, you can check how this content is displayed in the message using test profile data.

>[!IMPORTANT]
>
>Make sure to save your SMS message before you proceed to simulate the text message.

1. Click **[!UICONTROL Simulate Content]** at the top of the SMS authoring workspace.

1. From the _[!UICONTROL Simulate Content]_ page, click **[!UICONTROL Add People]**.

1. Use the _Simulate Content_ page to manage the leads used for your test profile.

   In the displayed list, you can search for and add any of the leads (up to 10 leads at a time) from the Marketo Engage lead database.

   To search, enter the whole email address and pressing _Enter_. The corresponding lead profile is displayed for selection.

   The preview updates to the personalization fields for the selected profile.

   All the added leads appear on the left.

   You can manage this list by adding more people and deleting individual leads from the profile listing (it does not remove them from the database).

1. Simulate content for a selected lead.

   Select any of the leads listed on the left. The SMS preview on the page updates for the selected lead.

   You can also select a lead from the selector above the preview space to update the SMS preview on the page for the corresponding lead.

1. To exit the _[!UICONTROL Simulate Content]_ page and return back to the SMS authoring workspace, click **[!UICONTROL Close]** at the top right.

## SMS consent management

Providing recipients the capability to unsubscribe from receiving communications from a brand and honoring this choice is a legal requirement. Failing to comply with these regulations introduces legal risks for your brand. This function also helps you avoid sending unsolicited communications to your recipients, which could cause them to mark your messages as spam and harm your reputation. 

When you provide this option, SMS recipients can reply with opt-in and opt-out keywords. All standard opt-in and opt-out keywords are supported and honored, and any custom keywords that are configured at the SMS service provider. When unsubscribed, the profiles are automatically removed from the audience of future marketing messages. 

Journey Optimizer B2B Edition provides the ability to manage opt-out in SMS messages using the following logic:

* By default, if a lead has opted out from receiving communications from you, the corresponding profile is excluded from subsequent SMS deliveries

* This lead consent coming from different sources (such as AEP or the SMS service provider) is synced to Journey Optimizer B2B Edition. Currently, it supports only a single consent state per lead at the instance level (a lead 'John Doe' is either subscribed to or unsubscribed from all promotional SMS in the instance). It does not currently support double opt-in on brand level/individual subscription list level consent.
