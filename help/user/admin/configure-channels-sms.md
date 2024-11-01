---
title: SMS configurations
description: Learn how to configure a connection to Experience Manager Assets repositories for use in Journey Optimizer B2B Edition content authoring.
feature: Setup
---
# Channels configuration

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

1. On the left navigation, expand the **[!UICONTROL Administrator]** section and click **[!UICONTROL Channels]**.

   ![Access the congfiguration of SMS API credentials](./assets/config-sms-api.png){width="800" zoomable="yes"}

1. In the navigation panel, select **[!UICONTROL API Credentials]**. 

   The page lists the available API configurations for your instance.
   
1. If needed, click the _Filter_ icon ( ![Show or hide filters icon](../assets/do-not-localize/icon-filter.svg) ) and select options to display the list of configured API credentials by the SMS service provider or creator.

   ![Click the Filter icon to refine the list of API credentials](./assets/config-sms-api-filter.png){width="600" zoomable="yes"}

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
