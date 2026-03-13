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

Use this checklist to complete Journey Optimizer B2B Edition setup on the simplified architecture.

## 1. Generate B2B namespaces and schemas

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | **Environment setup**: | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Download the namespace and schema auto-generation utility from GitHub. <li>Gather Experience Platform API credentials and required headers. | [Learn more](./data/namespaces-schemas.md#set-up-the-auto-generation-utility) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Apply environment values to your Postman environment. | [Learn more](./data/namespaces-schemas.md#environment-values) |
| | **Run the scripts**: | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Run the _Namespaces and Schemas_ generation utility in Postman and confirm namespaces and schemas are created. | [Learn more](./data/namespaces-schemas.md#run-the-scripts) |

## 2. Configure XDM fields and events

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | **Standard XDM classes**: Set up XDM Individual Profile and XDM Business Account classes. | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li> Edit managed fields - select fields to expose for journeys, buying groups, and email personalization. | [Learn more](./admin/xdm-field-management.md#standard-classes) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Edit updatable fields - select the schema and dataset and choose fields. | [Learn more](./admin/xdm-field-management.md#updatable-fields) |
| | **Relational schemas**: Select relational XDM class (Account many-to-one Custom Object). | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Ensure that schemas have Record behavior, Segmentation enabled, Many-to-one relationship, B2B Account reference, required keys, and associated dataset. | [Learn more](./admin/xdm-field-management.md#relational-schemas) |
| | **Events**: Configure Experience Platform event types and fields. | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure each Experience Platform event type and fields to be supported in journey decisioning/split paths. | [Learn more](./admin/configure-aep-events.md) | 

## 3. Configure tracking and email deliverability

To send emails from [!DNL Journey Optimizer B2B Edition] on the simplified architecture, configure the email tracking and deliverability in the attached [!DNL Marketo Engage] production instance and in the [!DNL Journey Optimizer B2B Edition] app.

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | **Initial setup** for the attached Marketo Engage instance | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <ul><li>Configure new CNAME for Tracking Links in DNS records | [Learn more](./start/email-protocols.md#create-dns-records-for-landing-pages-and-email) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <ul><li>Configure branding domains for the attached Marketo Engage instance | [Learn more](./start/branding-domains.md) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <ul><li>Configure DKIM and SPF to the attached Marketo Engage instance | [Learn more](./start/email-protocols.md#set-up-spf-and-dkim) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <ul><li>Set up DMARC | [Learn more](./start/email-protocols.md#set-up-dmarc) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <ul><li>Set up MX records for your domain | [Learn more](./start/email-protocols.md#set-up-mx-records-for-your-domain) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <ul><li>Add outbound IP addresses to allowlists | [Learn more](./start/email-protocols.md#outbound-ip-addresses) |
| | **Email setup** for the attached Marketo Engage instance | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure _From Email_ and _From Label_ | [Learn more](./start/email-setup.md#from-email-and-label) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure _Unsubscribe HTML_ and _Unsubscribe Text_ | [Learn more](./start/email-setup.md#unsubscribe-messaging) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure _View as Web Page HTML_ and _View as Web Page Text_ | [Learn more](./start/email-setup.md#view-as-web-page) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure _Custom Object Retrieval Limits_ | [Learn more](./start/email-setup.md#custom-object-retrieval-limits) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure _Custom Header Options_ | [Learn more](./start/email-setup.md#custom-header-options) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure _Email CC Settings_ | <!-- [Learn more](TBD) --> |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure _Bot Activity_ filtering | [Learn more](./start/email-setup.md#filter-email-bots) |
| | **Email channel configuration** for Journey Optimizer B2B Edition | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure _Communication Limits_ in Journey Optimizer B2B Edition | [Learn more](./admin/configure-channels-emails.md#communication-limits) |
| | **Additional configurations** | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | Configure _Location Settings_ for the attached Marketo Engage instance | <!-- [Learn more](TBD) --> |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | Define and configure which Binding Groups / IPs to move over | <!-- [Learn more](TBD) --> |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | Test Email Send | <!-- [Learn more](TBD) -->  |

## 4. Configure additional content channels

To support marketers for including other channels in their journeys, configure additional channels.

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | **SMS** channel configuration for Journey Optimizer B2B Edition. | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure each SMS account that you want to support. | |
| | **Landing pages** (Beta) channel configuration for Journey Optimizer B2B Edition. | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Complete the landing page settings to support marketers who author and publish these pages | [Learn more](./admin/landing-page-settings.md) |
| | **Web** (Beta) channel configuration to support personalized web experiences for Journey Optimizer B2B Edition | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure your business website to support the Adobe Experience Platform Web SDK. | [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Add web properties by a URL where the content is delivered. | [Learn more](./admin/configure-channels-web.md) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Instruct web experience authors to install the Adobe Experience Cloud Visual Editing Helper browser extension. | [Learn more](./content/web-experiences.md#install-the-visual-editing-helper-extension) |

## 5. Connect Marketo Engage instance to support journey actions (optional)

If you plan to supplement Journey Optimizer B2B Edition capabilities with campaigns and programs in Marketo Engage, set up support for Marketo Engage actions. These action allow your marketing teams to coordinate their _account-based_ marketing in Journey Optimizer B2B Edition and _lead-based_ marketing efforts in Marketo Engage.

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | **For each Marketo Engage instance** to support journey actions | |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Create the Marketo Engage custom service | [Learn more](./admin/marketo-actions-connect.md#create-the-marketo-engage-custom-service) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Add the integration in Journey Optimizer B2B Edition | [Learn more](./admin/marketo-actions-connect.md#add-the-integration) |

## 6. Enable user access

When provisioning is complete, sandboxes are bound, and initial setup tasks are complete, configure Journey Optimizer B2B Edition and Marketo Engage access for your team and users.

| | Task | Details and instructions |
| - | -- | ------------------------ |
| | | **Provide product access and permissions** for users|
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Create a Marketo Engage product profile in the Adobe Admin Console (new Marketo Engage instance only) |  [Learn more](./admin/user-management.md#create-the-marketo-engage-product-profile) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Add a user group for the profile | [Learn more](./admin/user-management.md#add-a-user-group-for-the-profile) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | <li>Configure B2B user roles | [Learn more](./admin/user-management.md#b2b-built-in-roles) |
| ![Checkbox](../assets/do-not-localize/icon-checkbox.svg){width="25"} | Add users or groups to the roles | [Learn more](./admin/user-management.md#add-users-to-a-role) |
