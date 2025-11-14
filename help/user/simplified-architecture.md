---
title: Simplified architecture setup
description: Set up Journey Optimizer B2B Edition on the simplified architecture. Configure XDM schemas, email/SMS channels, Marketo Engage journey actions, and users.
feature: Setup, Administration
role: Admin, Data Engineer
hide: yes
hidefromtoc: yes
---
# Simplified architecture setup

Adobe Journey Optimizer B2B Edition is now available using a simplified architecture. With this updated architecture, Journey Optimizer B2B Edition and Marketo Engage are no longer on the same system and same data store. Journey Optimizer B2B Edition receives data only from Adobe Experience Platform. However, it continues to rely on Marketo Engage entitlements and some configuration features to provision and configure the system. 

The simplified architecture is the foundation that unlocks new capabilities in Adobe Journey Optimizer B2B Edition:

* **Easily unify and scale your data:** The new platform supports complex data models, including custom objects, buying groups, and account events. 

* **Connect multiple Adobe Marketo Engage instances:** Manage and unify data from several Adobe Marketo Engage environments in one place.

* **Keeps your data safe:** Advanced privacy and security features that help protect your customer information. (_Coming soon_)

* **Built for the future:** This upgrade sets you up for ongoing improvements and innovation. 

For environments that are provisioned for this architecture, use the following guidelines for configuration.

## Namespaces and schemas

See [B2B namespaces and schemas](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo-namespaces) in the Experience Platform documentation for an overview. 

### Environment setup

Set up a Postman environment to support the B2B namespace and schema auto-generation utility.

* You can download the namespace and schema auto-generation utility collection and environment from the [GitHub repository](https://github.com/adobe/experience-platform-postman-samples/tree/master/Postman%20Collections/CDP%20Namespaces%20and%20Schemas%20Utility).

* For information about using Experience Platform APIs, including details for how to gather values for required headers and read sample API calls, see the [getting started with Experience Platform APIs](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-guide) guide.

* For information about how to generate your credentials for Experience Platform APIs, see the tutorial on [authenticating and accessing Experience Platform APIs](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication).

* For information about setting up Postman for Experience Platform APIs, see the detailed steps in [Postman in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/postman).

With an Experience Platform developer console and Postman set up, you can now start applying the appropriate environment values to your Postman environment.

### Run the scripts

With your Postman collection and environment setup, you can run the script through the Postman interface.

In the Postman interface, select the root folder of the auto-generator utility and then select **Run** from the top header.

When the Runner interface is displayed, ensure that all the checkboxes are selected and then select **Run Namespaces and Schemas Autogeneration Utility**.

A successful request creates the namespaces and schemas required for B2B.

## XDM field selection

You can manage the XDM fields that are available throughout the application in the Journey Optimizer B2B Edition UI. These fields help to streamline your instance by exposing only the fields that are relevant for building **_journeys_**, **_buying groups_**, or **_email personalizations_**.

### XDM classes

#### Standard classes

Use the steps below to define fields for standard XDM classes:

1. Navigate to **[!UICONTROL Administration] > [!UICONTROL Configurations]**.

1. In the navigation panel, select **[!UICONTROL XDM Classes]**.

1. Select the **[!UICONTROL Standard]** tab to view the available XDM classes:

   * XDM Individual Profile

   * XDM Business Account

#### Managed fields

Define which fields are available throughout the application.

1. Click the _More menu_ (**…**) icon and select **[!UICONTROL Edit managed fields]**.

1. Review the list of available fields (click the _Information_ icon for field metadata).

1. Select the fields that you want to include and clear selections for the fields that you don't need.

1. Use the **[!UICONTROL Only show selected fields]** slider to review your selections.

1. Click **[!UICONTROL Save]**.

#### Updatable fields

Choose which fields can be modified through **[!UICONTROL Update Account Profile]** or **[!UICONTROL Update Person Profile]** journey actions.

1. Click the _More menu_ (**…**) icon and select **[!UICONTROL Edit updatable fields]**.

1. Select **[!UICONTROL Schema]** and then **[!UICONTROL Dataset]**.

   These schemas and datasets are provided by your organization.

1. Review the list of updatable fields (click the _Information_ icon for metadata). 

   Only the managed fields are editable.

1. Select the fields that you want to make available for update from journeys.

1. Click **Save**

### Relational schemas

Select [relational schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational) for use in **_journey decisioning_** and **_personalization_**. Currently, these schemas are for Custom Object use cases. In the future, relational schemas can also be used for other object use cases. 

1. Select the **[!UICONTROL Relational]** tab.

1. Click **[!UICONTROL Select relational XDM class]**.

   Currently, only Account many-to-one Custom Object is supported.

1. Review the list of schema fields (click the _information_ icon to view the metadata).

1. Select the fields that you want to include.

1. Use the **[!UICONTROL Only show selected fields]** slider to review your selections.

1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>Note that relational schemas must have the following configurations:
>
><li>Behavior: Record
> <li>Segmentation: Enabled
> <li>Relationship Type: Many-to-one
> <li>Reference Schema: [B2B Account - XDM Business Account schema](https://experienceleague.adobe.com/en/docs/platform-learn/tutorials/schemas/create-schemas-for-b2b-data)
> <li>Required Fields: Primary key, Foreign key, and Version descriptor
> <li>Associated Dataset: Defined and mapped to the schema

### Events

Select the Experience Events to use in **_journey decisioning_**.

1. Select the **[!UICONTROL Events]** tab.

1. Click **[!UICONTROL Select experience event]**.

1. Click **[!UICONTROL Select event type]**, choose the event type, click **[!UICONTROL Select]**.

1. Click **[!UICONTROL Select fields]**, choose the fields that you need, click **[!UICONTROL Select]**.

1. Click **[!UICONTROL Save]**.

## Email configuration

The following should be configured to send emails out of Journey Optimizer B2B Edition.  

[https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols)

### Protocols for tracking and email delivery

1. [Create DNS records for email](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#create-dns-records-for-landing-pages-and-email)

1. [Set up SPF and DKIM](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-spf-and-dkim)

1. [Set up DMARC](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-dmarc)

1. [Set up MX records for your domain](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-mx-records-for-your-domain)

1. [Add Outbound IP addresses to allowlists](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#outbound-ip-addresses)

1. If you need to share the dedicated IP pool, reach out to the deliverability team on the feasibility and assisted setup.

### Email channel configurations

In the simplified architecture, email settings are configured from the Marketo Engage UI. Complete the email related setup steps: [https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps)

[https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-emails](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-emails)

### Communication limits

1. In the left navigation, choose **[!UICONTROL Administration]** > **[!UICONTROL Channels]**.

1. In the navigation panel, select **[!UICONTROL Communication Limit]**.

1. Create a global communication limit rule set (this rule set is created by default in every Journey Optimizer B2B Edition instance).

   There is no communication limit if the global rule set is not created.

<!-- In the future, you can also add local communication limit rule sets (AJO B2C doc can be found here [https://experienceleague.adobe.com/en/docs/journey-optimizer/using/conflict-prioritization/capping-rules/rule-sets](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/conflict-prioritization/capping-rules/rule-sets). We may need a small update for our B2B version.) -->

### Shared communication limits

Within the new architecture, Journey Optimizer B2B Edition and Marketo Engage have independent communication limits by default.

If you want the Marketo Engage instance to share the communication limit set in the Journey Optimizer B2B Edition instance, reach out to Adobe Support for assistance in configuration or open a Support ticket. Upon request, the Engineering team can enable the sharing of communication limits between Journey Optimizer B2B Edition and one or more  Marketo Engage instances.

Currently, the shared communication limit in the Marketo Engage instance must be set up through an API call.

For example, when:

* The munchkinId of the Journey Optimizer B2B Edition instance is `JKL-567-MNO`.
* The munchkinId of the Marketo Engage instance is `ABC-123-DEF` and it is in the SJ datacenter

The API request should look similar to the following:

```
curl --location --request POST 'http://sjrest2a.marketo.org/rest/v1/fm.json?_munchkinId=ABC-123-DEF&featureName=Mktmail%20Config&paramName=ajoB2bMappingMunchkinId&dataType=string&value=JKL-567-MNO'
```

## SMS channel configuration

See [_SMS configurations_](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-sms) for detailed information. 

## Marketo Engage actions from journeys

You can configure one or more remote **_Marketo Engage_** instances for use with the following journey actions:

* Add to Marketo List
* Remove from Marketo List
* Add to Marketo Request Campaign

Complete the following steps for configuring these connections:

1. Navigate to **[!UICONTROL Administration] > [!UICONTROL Configurations]**.

1. In the navigation panel, select **[!UICONTROL XDM Classes]**.

1. Select the **[!UICONTROL Integrations]** tab.

1. Click **[!UICONTROL Create connection]**.

1. Enter the **[!UICONTROL Name]** and **[!UICONTROL Description]**.

1. Select **[!UICONTROL Update policy]** for matching person records.

1. Enter **[!UICONTROL Munchkin ID]**, **[!UICONTROL Client ID]**, **[!UICONTROL Client Secret]**, and click **[!UICONTROL Connect to Marketo]**.

1. Click **[!UICONTROL Create]**.

## User onboarding

See the [User management](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/user-management) page for an overview.

### Existing user groups

If all the existing Journey Optimizer B2B Edition users need access to the new architecture, use the existing Journey Optimizer B2B Edition user group. A system administrator or product administrator can perform the following steps.

1. Create a product profile in the dedicated Marketo Engage.

1. Add an existing user group to the created product profile.

The profiles grant all roles and permissions already assigned to that user group, which should already be configured for the users to access Journey Optimizer B2B Edition. If only a subset of users should access the new architecture, complete the steps outlined below. More details in the [current documentation](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/user-management).

### Create a new user group

1. Create a product profile in the dedicated Marketo Engage instance.
1. Create a user group for new users.
1. Select and assign the required product profiles to the user group:

   * Marketo Engage profile that you created
   * Adobe Experience Platform profiles
      * AEP-Default-All-Users
      * Adobe Experience Platform Data Collection
      * Data Collection All Access

1. Add the users to the user group.
1. Add a new user group to Journey Optimizer B2B Edition roles in Experience Platform.
