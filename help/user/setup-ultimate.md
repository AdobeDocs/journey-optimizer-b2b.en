---
title: Setup checklist
description: Set up Journey Optimizer B2B Edition. Configure XDM schemas, email/SMS channels, Marketo Engage journey actions, and users.
feature: Setup, Administration
role: Admin, Developer
exl-id: 81232976-09d6-4e10-a034-5c193a63b7df
---
# Setup checklist

Adobe Journey Optimizer B2B Edition is built on Adobe Experience Platform. With this implementation, Journey Optimizer B2B Edition and Marketo Engage are not on the same system and same data store. Journey Optimizer B2B Edition receives data from Adobe Experience Platform. However, it continues to rely on Marketo Engage entitlements and some backend features, such as email delivery, to provision and configure the system.

<!-- 
>>[!NOTE]
>
>Earlier documentation referred to this deployment as the *simplified architecture*. That model is now the Journey Optimizer B2B Edition Ultimate implementation. 
-->

This implementation is the foundation that unlocks capabilities in Journey Optimizer B2B Edition:

* **Easily unify and scale your data:** The platform supports complex data models, including custom objects, buying groups, and account events. 

* **Connect multiple Adobe Marketo Engage instances:** Manage and unify data from several Marketo Engage environments in one place.

* **Keep your data safe:** Advanced privacy and security features that help protect your customer information. (_Coming soon_)

* **Built for the future:** This setup supports ongoing improvements and innovation. 

Use the following guidelines for configuration.

Use this checklist to complete Journey Optimizer B2B Edition setup.

## 1. Generate B2B namespaces and schemas

<table>
<thead>
<tr>
<th colspan="2">Task</th>
<th>Details and instructions</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Environment setup:</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Download the namespace and schema auto-generation utility from GitHub.</td>
<td><a href="./data/namespaces-schemas.md#set-up-the-auto-generation-utility">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Gather Experience Platform API credentials and required headers.</td>
<td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-guide">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Apply environment values to your Postman environment.</td>
<td><a href="./data/namespaces-schemas.md#environment-values">Learn more</a></td>
</tr>
<tr>
<td colspan="2"><strong>Run the scripts:</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Run the <em>Namespaces and Schemas</em> generation utility in Postman and confirm namespaces and schemas are created.</td>
<td><a href="./data/namespaces-schemas.md#run-the-scripts">Learn more</a></td>
</tr>
</tbody>
</table>

## 2. Configure XDM fields and events

<table>
<thead>
<tr>
<th colspan="2">Task</th>
<th>Details and instructions</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Standard XDM classes</strong>: Set up XDM Individual Profile and XDM Business Account classes.</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Select managed fields to expose for journeys, buying groups, and email personalization.</td>
<td><a href="./admin/xdm-field-management.md#standard-classes">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Edit updatable fields for schemas.</td>
<td><a href="./admin/xdm-field-management.md#updatable-fields">Learn more</a></td>
</tr>
<tr>
<td colspan="2"><strong>Relational schemas</strong>: Select relational XDM class (Account many-to-one Custom Object).</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Ensure that schemas have the required configuration values.</td>
<td><a href="./admin/xdm-field-management.md#relational-schemas">Learn more</a></td>
</tr>
<tr>
<td colspan="2"><strong>Events</strong>: Configure Experience Platform event types and fields.</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure each Experience Platform event type with fields to be supported in journey decisioning/split paths.</td>
<td><a href="./admin/configure-aep-events.md">Learn more</a></td>
</tr>
</tbody>
</table> 

## 3. Configure tracking and email deliverability

To send emails from [!DNL Journey Optimizer B2B Edition], configure the email tracking and deliverability in the attached [!DNL Marketo Engage] production instance and in the [!DNL Journey Optimizer B2B Edition] app.

<table>
<thead>
<tr>
<th colspan="2">Task</th>
<th>Details and instructions</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Initial setup</strong> for the attached Marketo Engage instance</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure new CNAME for Tracking Links in DNS records</td>
<td><a href="./start/email-protocols.md#create-dns-records-for-landing-pages-and-email">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure branding domains for the attached Marketo Engage instance</td>
<td><a href="./start/branding-domains.md">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure DKIM and SPF to the attached Marketo Engage instance</td>
<td><a href="./start/email-protocols.md#set-up-spf-and-dkim">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Set up DMARC</td>
<td><a href="./start/email-protocols.md#set-up-dmarc">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Set up MX records for your domain</td>
<td><a href="./start/email-protocols.md#set-up-mx-records-for-your-domain">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Add outbound IP addresses to allowlists</td>
<td><a href="./start/email-protocols.md#outbound-ip-addresses">Learn more</a></td>
</tr>
<tr>
<td colspan="2"><strong>Email setup</strong> for the attached Marketo Engage instance</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>From Email</em> and <em>From Label</em> (optional)</td>
<td><a href="./start/email-setup.md#from-email-and-label">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Unsubscribe HTML</em> and <em>Unsubscribe Text</em></td>
<td><a href="./start/email-setup.md#unsubscribe-messaging">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>View as Web Page HTML</em> and <em>View as Web Page Text</em></td>
<td><a href="./start/email-setup.md#view-as-web-page">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Custom Object Retrieval Limits</em></td>
<td><a href="./start/email-setup.md#custom-object-retrieval-limits">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Custom Header Options</em></td>
<td><a href="./start/email-setup.md#custom-header-options">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Bot Activity</em> filtering</td>
<td><a href="./start/email-setup.md#filter-email-bots">Learn more</a></td>
</tr>
<tr>
<td colspan="2"><strong>Email channel configuration</strong> for Journey Optimizer B2B Edition</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Communication Limits</em> in Journey Optimizer B2B Edition</td>
<td><a href="./admin/configure-channels-emails.md#communication-limits">Learn more</a></td>
</tr>
</tbody>
</table>

<!--
 TBD for later

<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Email CC Settings</em></td>
<td>[Learn more](TBD)</td>
</tr>

<tr>
<td colspan="2"><strong>Additional configurations</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Location Settings</em> for the attached Marketo Engage instance</td>
<td>< [Learn more](TBD)</td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Define and configure which Binding Groups / IPs to move over</td>
<td>[Learn more](TBD)</td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Test Email Send</td>
<td>[Learn more](TBD)</td>
</tr>
-->

## 4. Configure additional content channels

To support marketers for including other channels in their journeys, configure additional channels.

<table>
<thead>
<tr>
<th colspan="2">Task</th>
<th>Details and instructions</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>SMS</strong> channel configuration for Journey Optimizer B2B Edition.</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure each SMS account that you want to support.</td>
<td><a href="./admin/configure-channels-sms.md">Learn more</a></td>
</tr>
<tr>
<td colspan="2"><strong>Landing pages</strong> (Beta) channel configuration for Journey Optimizer B2B Edition.</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Complete the landing page settings to support marketers who author and publish these pages</td>
<td><a href="./admin/landing-page-settings.md">Learn more</a></td>
</tr>
<tr>
<td colspan="2"><strong>Web</strong> (Beta) channel configuration for Journey Optimizer B2B Edition</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure your business website to support the Adobe Experience Platform Web SDK.</td>
<td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Add web properties by a URL where the content is delivered.</td>
<td><a href="./admin/configure-channels-web.md">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Instruct web experience authors to install the Adobe Experience Cloud Visual Editing Helper browser extension.</td>
<td><a href="./content/web-experiences.md#install-the-visual-editing-helper-extension">Learn more</a></td>
</tr>
</tbody>
</table>

## 5. Connect Marketo Engage instance to support journey actions (optional)

If you plan to supplement Journey Optimizer B2B Edition capabilities with campaigns and programs in Marketo Engage, set up support for Marketo Engage actions. These action allow your marketing teams to coordinate their _account-based_ marketing in Journey Optimizer B2B Edition and _lead-based_ marketing efforts in Marketo Engage.

<table>
<thead>
<tr>
<th colspan="2">Task</th>
<th>Details and instructions</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>For each Marketo Engage instance</strong> to support journey actions</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Create the Marketo Engage custom service</td>
<td><a href="./admin/marketo-actions-connect.md#create-the-marketo-engage-custom-service">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Add the integration in Journey Optimizer B2B Edition</td>
<td><a href="./admin/marketo-actions-connect.md#add-the-integration">Learn more</a></td>
</tr>
</tbody>
</table>

## 6. Enable user access

When provisioning is complete, sandboxes are bound, and initial setup tasks are complete, configure Journey Optimizer B2B Edition and Marketo Engage access for your team and users.

<table>
<thead>
<tr>
<th colspan="2">Task</th>
<th>Details and instructions</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Provide product access and permissions</strong> for users</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Create a Marketo Engage product profile in the Adobe Admin Console (new Marketo Engage instance only)</td>
<td><a href="./admin/user-management.md#marketo-engage-profile">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Add a user group for the profile</td>
<td><a href="./admin/user-management.md#add-user-group">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure B2B user roles</td>
<td><a href="./admin/user-management.md#b2b-built-in-roles">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Add users or groups to the roles</td>
<td><a href="./admin/user-management.md#add-users-to-a-role">Learn more</a></td>
</tr>
</tbody>
</table>
