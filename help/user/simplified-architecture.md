---
title: Simplified architecture setup
description: Set up Journey Optimizer B2B Edition on the simplified architecture. Configure XDM schemas, email/SMS channels, Marketo Engage journey actions, and users.
feature: Setup, Administration
role: Admin, Data Engineer
exl-id: 81232976-09d6-4e10-a034-5c193a63b7df
---
# Simplified architecture setup

Adobe Journey Optimizer B2B Edition is now available using a simplified architecture. With this architecture, Journey Optimizer B2B Edition and Marketo Engage are no longer on the same system and same data store. Journey Optimizer B2B Edition receives data only from Adobe Experience Platform. However, it continues to rely on Marketo Engage entitlements and some backend features, such as email delivery, to provision and configure the system.

The simplified architecture is the foundation that unlocks new capabilities in Journey Optimizer B2B Edition:

* **Easily unify and scale your data:** The new platform supports complex data models, including custom objects, buying groups, and account events. 

* **Connect multiple Adobe Marketo Engage instances:** Manage and unify data from several Marketo Engage environments in one place.

* **Keeps your data safe:** Advanced privacy and security features that help protect your customer information. (_Coming soon_)

* **Built for the future:** This upgrade sets you up for ongoing improvements and innovation. 

For environments that are provisioned for this architecture, use the following guidelines for configuration.

## Setup checklist

Use this checklist to complete Journey Optimizer B2B Edition setup on the simplified architecture.

### 1. Generate B2B namespaces and schemas

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | **Environment setup**: | |
| | <li>Download the namespace and schema auto-generation utility from GitHub. <li>Gather Experience Platform API credentials and required headers. | [Learn more](./data/namespaces-schemas.md#set-up-the-auto-generation-utility) |
| | <li>Apply environment values to your Postman environment. | [Learn more](./data/namespaces-schemas.md#environment-values) |
| | **Run the scripts**: | |
| | <li>Run the _Namespaces and Schemas_ generation utility in Postman and confirm namespaces and schemas are created. | [Learn more](./data/namespaces-schemas.md#run-the-scripts) |

### 2. Configure XDM fields and events

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | **Standard XDM classes**: Set up XDM Individual Profile and XDM Business Account classes. | |
| | <li> Edit managed fields - select fields to expose for journeys, buying groups, and email personalization. | [Learn more](./admin/xdm-field-management.md#standard-classes) |
| | <li>Edit updatable fields - select the schema and dataset and choose fields. | [Learn more](./admin/xdm-field-management.md#updatable-fields) |
| | **Relational schemas**: Select relational XDM class (Account many-to-one Custom Object). | |
| | <li> Ensure that schemas have Record behavior, Segmentation enabled, Many-to-one relationship, B2B Account reference, required keys, and associated dataset. | [Learn more](./admin/xdm-field-management.md#relational-schemas) |
| | **Events**: Configure Experience Platform event types and fields for journey decisioning/split paths. | [Learn more](./admin/configure-aep-events.md) | 

### 3. Configure tracking and email deliverability

To send emails from [!DNL Journey Optimizer B2B Edition] on the simplified architecture, configure the email channel and deliverability in the associated [!DNL Marketo Engage] production instance and in the [!DNL Journey Optimizer B2B Edition] app.

[Marketo Engage setup steps](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps) 
[Configure protocols for Marketo Engage](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/configure-protocols-for-marketo)

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | **Initial setup** for the attached Marketo Engage instance | |
| | <li>Configure new CNAME for Tracking Links in DNS records | [Learn more](./start/email-protocols.md#create-dns-records-for-landing-pages-and-email) |
| | <li>Configure branding domains for the attached Marketo Engage instance | [Learn more](./start/branding-domains.md) |
| | <li>Configure DKIM and SPF to the attached Marketo Engage instance | [Learn more](./start/email-protocols#set-up-spf-and-dkim) |
| | <li>Set up DMARC | [Learn more](./start/email-protocols#set-up-dmarc) |
| | <li>Set up MX records for your domain | [Learn more](./start/email-protocols#set-up-mx-records-for-your-domain) |
| | <li>Add outbound IP addresses to allowlists | [Learn more](./start/email-protocols#outbound-ip-addresses) |
| | **Email parameters and filtering** for the attached Marketo Engage instance | |
| | <li>Configure _From_ email | <!-- [Learn more](TBD) --> |
| | <li>Configure _From_ label | <!-- [Learn more](TBD) --> |
| | <li>Configure _Unsubscribe HTML_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Unsubscribe Text_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _View as Web Page HTML_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _View as Web Page Text_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Custom Object Retrieval Limits_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Custom Header Options_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Text Editor Settings_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Email Editor Settings_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Email CC Settings_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Bot Activty_ filtering | [Learn more](./start/email-settings.md#filter-email-bot-activity) |
| | **Set up email channels** for Journey Optimizer B2B Edition | |
| | <li>Configure _Communciation Limits_ in Journey Optimizer B2B Edition | [Learn more](./admin/configure-channels-emails.md#communication-limits) |
| | Configure _Location Settings_ in the attached Marketo Engage instance |  <!-- [Learn more](TBD) --> |
| | Define and configure which Binding Groups / IPs to move over | <!-- [Learn more](TBD) --> |
| | Test Email Send | <!-- [Learn more](TBD) -->  |

[Assess current docs](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-emails). 

<!-- assess docs for what we need

* [ ] **Email header parameters (in Marketo Engage) https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/change-the-default-from-email-and-from-label 
https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/edit-the-unsubscribe-message 
https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/edit-the-view-as-web-page-message -->

Configure default from address/label, unsubscribe message, and view-as-web-page message.

### 4. Configure SMS channels in Journey Optimizer B2B Edition

* [ ] **SMS configuration:** Complete [SMS configurations](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-sms) as needed.

### 5. Connect Marketo Engage instance to support journey actions

* [ ] **Create connection(s):** **[!UICONTROL Administration]** > **[!UICONTROL Configurations]** > **[!UICONTROL XDM Classes]** > **[!UICONTROL Integrations]** tab > **[!UICONTROL Create connection]**.
  * [ ] Enter name and description; select update policy; enter Munchkin ID, Client ID, Client Secret; Connect to Marketo; Create.
  * [ ] Repeat for each remote Marketo Engage instance used for Add to List, Remove from List, Add to Request Campaign.

### 6. Enable user access for Journey Optimizer B2B Edition and Marketo Engage 

* [ ] **Existing user groups:** Create a product profile for the dedicated Marketo Engage instance; add existing Journey Optimizer B2B Edition user group to that product profile.
* [ ] **New user group (optional):** Create product profile in dedicated Marketo Engage; create user group; assign product profiles (Marketo Engage, AEP-Default-All-Users, Adobe Experience Platform Data Collection, Data Collection All Access); add users; add user group to Journey Optimizer B2B Edition roles in Experience Platform.

<!-- review for anything that is not covered

## Other email configuration

Complete the following steps based on the referenced documentation.

### Initial setup and protocols

* [Marketo Engage setup steps](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps)
* [Configure protocols for Marketo Engage](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/configure-protocols-for-marketo)


* [Configure email channels in Journey Optimizer B2B Edition](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-emails)

### Email header parameters

Configure the default from address and labels, unsubscribe message, and view-as-web-page message in the attached [!DNL Marketo Engage] instance:

* [Change the default from email and from label](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/change-the-default-from-email-and-from-label)
* [Edit the unsubscribe message](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/edit-the-unsubscribe-message)
* [Edit the view as web page message](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/edit-the-view-as-web-page-message)

### Email bot activity filtering

* [Filtering email bot activity](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/filtering-email-bot-activity)

### Protocols for tracking and email delivery

1. [Create DNS records for email](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#create-dns-records-for-landing-pages-and-email)
1. [Set up SPF and DKIM](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-spf-and-dkim)
1. [Set up DMARC](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-dmarc)
1. [Set up MX records for your domain](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-mx-records-for-your-domain)
1. [Add outbound IP addresses to allowlists](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#outbound-ip-addresses)

If you need to share a dedicated IP pool, contact the Adobe deliverability team to confirm feasibility and get help with setup.


## SMS channel configuration

See [_SMS configurations_](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-sms) for detailed information.

-->
