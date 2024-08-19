---
title: SMS Authoring
description: Learn how to send text messages (SMS) to your customers on their mobile devices, and to personalize and preview messages in text format from the SMS editor.
feature: SMS Authoring, Content
exl-id: bd648253-74de-4083-a37a-ab7ceaea2746
---
# SMS authoring

Use Adobe Journey Optimizer B2B Edition to send text messages (SMS) to your customers on their mobile devices. You can create, personalize, and preview messages in text format from the SMS editor. 

## SMS configurations

Adobe Journey Optimizer B2B Edition sends text messages through SMS service providers (or SMS gateway providers). Before creating your SMS message, configure your service provider from the _Administrator_ settings.

### SMS gateway service providers

Adobe Journey Optimizer B2B Edition currently integrates with third-party providers who offer text messaging services independently. Supported providers for text messaging are Sinch, Twilio, and Infobip. 

Before you configure an SMS channel in Adobe Journey Optimizer B2B Edition, you must create an account with one of these providers to get your API Token and Service ID. These credentials are required to configure the connection between Adobe Journey Optimizer B2B Edition and the applicable provider.

>[!IMPORTANT]
>
>Your use of text messaging services is subject to additional terms and conditions from the applicable provider. As third-party solutions, Sinch, Twilio, and Infobip are available to Adobe Journey Optimizer B2B Edition users through an integration. Adobe does not control, and is not responsible for third-party products. For any issues or requests for assistance related to the text messaging services (SMS), contact your provider.

### Verify an existing SMS API configuration

>[!NOTE]
>
>The described settings are accessible only to the users with SMS Admin privileges.

On the left navigation, expand the **[!UICONTROL Administrator]** section and click **[!UICONTROL Configuration]**.

![Access the congfiguration of AMA API credentials](./assets/config-sms-api.png){width="800" zoomable="yes"}

The page lists the available API configurations for your instance. You can filter the displayed API credentials by the SMS service provider or creator.

![Click the filter icon to filter the list of API credentials](./assets/config-sms-api-filter.png){width="500"}

### Create a new API credentials for an SMS service provider

>[!BEGINTABS]

>[!TAB Sinch]

_To configure Sinch as your SMS provider with Adobe Journey Optimizer B2B Edition:_

1. On the left navigation, expand the **[!UICONTROL Administrator]** section and click **[!UICONTROL Configuration]**.

1. Click the **[!UICONTROL Create new API credentials]** at the top-right of the _[!UICONTROL API credentials]_ list.

1. Configure your SMS API credentials:

   ![Configure the Sinch SMS API credentials](./assets/config-sms-api-sinch.png){width="500"}

   * **[!UICONTROL SMS vendor]** - Choose `Sinch` as the SMS provider.

   * **[!UICONTROL Name]** - Enter a name for your API credential.

   * **[!UICONTROL Service ID]** and **[!UICONTROL API Token]** - Access the APIs page from your Sinch account (you can find your credentials under the SMS tab).

   For more information about finding this information for your Sinch account, see the [Sinch developer documentation](https://developers.sinch.com/docs/sms/getting-started/#2-get-credentials)

1. Click **[!UICONTROL Submit]** when the configuration details of your API credentials are complete.

>[!TAB Twilio]

_To configure Twilio as your SMS provider with Adobe Journey Optimizer B2B Edition:_

1. On the left navigation, expand the **[!UICONTROL Administrator]** section and click **[!UICONTROL Configuration]**.

1. Click the **[!UICONTROL Create new API credentials]** at the top-right of the _[!UICONTROL API credentials]_ list.

1. Configure your SMS API credentials:

   ![Configure the Twilio SMS API credentials](./assets/config-sms-api-twilio.png){width="500"}

   * **[!UICONTROL SMS vendor]** - Choose `Twilio` as the SMS provider.

   * **[!UICONTROL Name]** - Enter a name for your API credential definition.

   * **[!UICONTROL Account SID]** and **[!UICONTROL Auth Token]** - Access the _Account Info_ pane of your Twilio Console Dashboard page to find your credentials.

   For more information about finding this information for your Twilio account, see the [Twilio Help Center](https://help.twilio.com/articles/14726256820123-What-is-a-Twilio-Account-SID-and-where-can-I-find-it-).

1. Click **[!UICONTROL Submit]** at the top-right of the page when the configuration details of your API credentials are complete.

>[!TAB Infobip]

_To configure Infobip as your SMS provider with Adobe Journey Optimizer B2B Edition:_

1. On the left navigation, expand the **[!UICONTROL Administrator]** section and click **[!UICONTROL Configuration]**.

1. Click the **[!UICONTROL Create new API credentials]** at the top-right of the _[!UICONTROL API credentials]_ list.

1. Configure your SMS API credentials:

   ![Configure the Infobip SMS API credentials](./assets/config-sms-api-infobip.png){width="500"}

   * **[!UICONTROL SMS vendor]** - Choose `Infobip` as the SMS provider.

   * **[!UICONTROL Name]** - Enter a name for your API credential definition.

   * **[!UICONTROL API base URL]** and **[!UICONTROL API key]** - Access your web interface homepage or the API key management page for your Infobip account to find your credentials.

   For more information about finding this information for your Infobip account, see the [Infobip documentation](https://www.infobip.com/docs/api/_blank).

1. Click **[!UICONTROL Submit]** at the top-right of the page when the configuration details of your API credentials are complete.

>[!ENDTABS]

When you click _[!UICONTROL Submit]_, the credentials are immediately validated and saved, redirecting you to the _[!UICONTROL API credentials]_ listing page. If the submitted credentials are invalid, the system displays an error message on the listing page. In this case, you can choose to cancel the configuration, or to update it and submit again.

## Add an SMS action in an account journey

You can set up text message deliveries in an Account Journey when you add a _[!UICONTROL Take an action]_ node and do the following:

1. For the _[!UICONTROL Action on]_ target, choose **[!UICONTROL People]**.

1. For the _[!UICONTROL Action on people]_, choose **[!UICONTROL Send SMS]**.

   ![Take an action - send sms](assets/journey-node-send-sms.png){width="800" zoomable="yes"}

1. At the bottom of the _[!UICONTROL Take an action]_ panel, click **[!UICONTROL Create SMS]**.

1. In the dialog, enter a unique **[!UICONTROL Name]** for the email and a **[!UICONTROL Subject line]**.

   ![Create new SMS dialog](assets/create-new-sms.png){width="500"}

## Create the SMS message

>[!IMPORTANT]
>
>**SMS consent management**<br/>
><br/>
>In accordance with the industry standards and regulations, all SMS marketing messages must contain a way for the recipients to unsubscribe easily. To do this, SMS recipients can reply with opt-in and opt-out keywords. All standard opt-in and opt-out keywords are supported and honored. In addition, any custom keywords configured for your SMS service provider account are supported and honored.

1. Enter the text that you want to send in the **[!UICONTROL Message]** field.

   You can create a message of up to 1600 characters, with every 160 characters considered as a single SMS message.

1. **Personalize the text message**.

   At anytime while authoring the text message, click the _Personalize_ icon to the right of the text message box.

   ![Click the Personalize icon to add tokens to the message](./assets/sms-message-personalize-icon.png){width="800" zoomable="yes"}
   
   The displayed page provides access to your Adobe Marketo Engage Lead and System tokens. Both standard and custom tokens are included. You can use the Search bar to locate the token you need, or navigate through the folder tree to find and select any of the lead/system tokens.

   Place your cursor at the location in the message where you want to add the token. Add a token by clicking the plus ( **+** ) symbol next to it. If you want to add the token with a fallback (default that appears in case that field is not available for a lead), click the ellipsis ( **...** ) and choose **[!UICONTROL Insert with fallback text]**.

   ![Click the ellipses to use a fallback for the token](./assets/sms-message-personalize-ellipsis-fallback.png){width="700" zoomable="yes"}

   In the _[!UICONTROL Enter fallback value]_ dialog, enter the text that appears as a fallback and then click **[!UICONTROL Add]**.

   ![Enter the fallback text for the token](./assets/sms-message-personalize-fallback-text.png){width="400"}

   When your personalization tokens are placed, click **[!UICONTROL Save]** to save changes and return to the main SMS authoring workspace. You can continue to edit the message with the tokens as needed. 

1. **Add URLs to the text message**.

   After defining your content, you can add URLs to your message by clicking the _Link_ icon.
   
   This action opens a dialog, where you can choose one of two types of URLs to link: 

   * **[!UICONTROL External URL]** - This type is any external URL that you enter in the text box.
   * **[!UICONTROL Landing Page]** - Choose this option to select any of the approved Adobe Marketo Engage Design Studio landing pages from your Marketo Engage instance.

   The dialog also includes options for the URL links:

   * **[!UICONTROL Shorten URL]** - Select this checkbox to _shorten_ the URL, which is necessary for tracking. For a landing page, it uses the Marketo Engage subdomain for the shortened URL. A sample of the shortened URL format is displayed. The actual URL is created when the SMS is sent to the recipient.

   * **[!UICONTROL Include mkt_tok]** - Select this checkbox to track activity against a user. 
  
   When the link options are complete, click **[!UICONTROL Add]** to save the changes and add the URL link to the SMS message.

## Set the SMS properties

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

## Simulate the text message content {#preview-test}

>[!CONTEXTUALHELP]
>id="ajo-b2b_sms_preview_simulate"
>title="Check how your content is rendering"
>abstract="Once your content has been defined, you can preview it and check if the rendering is correct according to the channel you are using."

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

   Select any of the leads listed on the left and the SMS preview on the page updates for the corresponding lead.

   You can also select a lead from the selector above the preview space to update the SMS preview on the page for the corresponding lead.

1. To exit the _[!UICONTROL Simulate Content]_ page and return back to the SMS authoring workspace, click **[!UICONTROL Close]** at the top right.

## SMS consent management

Providing recipients the capability to unsubscribe from receiving communications from a brand and honoring this choice is a legal requirement. Failing to comply with these regulations introduces legal risks for your brand. This function also helps you avoid sending unsolicited communications to your recipients, which could cause them to mark your messages as spam and harm your reputation. 

When you provide this option, SMS recipients can reply with opt-in and opt-out keywords. All standard opt-in and opt-out keywords are supported and honored, and any custom keywords that are configured at the SMS service provider. When unsubscribed, the profiles are automatically removed from the audience of future marketing messages. 

Journey Optimizer B2B Edition provides the ability to manage opt-out in SMS messages using the following logic:

* By default, if a lead has opted out from receiving communications from you, the corresponding profile is excluded from subsequent SMS deliveries

* This lead consent coming from different sources (such as AEP or the SMS service provider) is synced to Journey Optimizer B2B Edition. Currently, it supports only a single consent state per lead at the instance level (a lead 'John Doe' is either subscribed to or unsubscribed from all promotional SMS in the instance). It does not currently support double opt-in on brand level/individual subscription list level consent.
