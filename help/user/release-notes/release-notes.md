---
title: Journey Optimizer B2B Edition Release Rotes
description: Learn about the latest features and enhancements in Adobe Journey Optimizer B2B Edition.
role: User, Admin
exl-id: 7d3f1c26-d8a6-4065-a70f-5b30cb975dc8
---
# Journey Optimizer B2B Edition release notes

Adobe Journey Optimizer B2B Edition continuously delivers new features, enhancements to existing features, and bug fixes.

Journey Optimizer B2B Edition is built natively on [!DNL Adobe Experience Platform] and inherits from its latest innovations and improvements. Learn more about these changes in [Adobe Experience Platform Release Notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/latest){target="_blank"}.

Review the [product description](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} for information about entitlements, performance guardrails, and limitations.

<!-- hold for later release 

| Feature | Landing pages | You can now create and publish landing pages in Journey Optimizer B2B Edition to support your journeys and programs. _(Previously a Beta program feature.)_ [Learn more](../content/landing-pages.md) |
| Feature | Forms | You can now create and publish re-usable form components to enable data submission from landing pages that are created and published in Journey Optimizer B2B Edition. _(Previously a Beta program feature.)_ [Learn more](../content/forms.md) |

-->

## 2025.8 release notes

**Deployment date**: August 26, 2025

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | Person engagement score filters for roles templates and journeys | You can now use _Person engagement score_ as a filter in Roles templates that are used to create buying groups and in split path journey nodes. [Learn more](../buying-groups/buying-groups-role-templates.md#add-the-template-roles) |
| Feature | Buying groups custom roles configuration | You now have the flexibility to configure custom roles for buying groups, which allows you to define the roles specific to your use cases. [Learn more](../buying-groups/default-custom-roles.md)  |
| Feature | Engagement score weighting configuration | You can now assign weights to the activities that influence the buying group engagement score. This feature includes defining your own custom score models and changing the active model that influences engagement score calculations. <!-- [Learn more](../admin/engagement-score-weighting.md)  --> |
| Enhancement | Conditional content for fragments | You can now use the conditional content tools for visual fragment design. [Learn more](../content/conditional-content.md) |
| Enhancement | Engagement score updates | Buying group engagement score logic is updated to normalize the scores. Additionally, you can work with member-level engagement scores, as well as collective engagement scores for the whole buying group. [Learn more](../buying-groups/engagement-scores.md) |
| Enhancement | Active journey observability - accounts at each node | For an active account journey, you can access a list of the accounts that have reached each account node in the journey. |

>[!NOTE]
>
>The release changes begin deployment on August 26, 2025, with a phased rollout of each feature. Release dates for features and enhancements are subject to change. 

## 2025.6 release notes

**Deployment date**: July 15, 2025

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | Integration with GenStudio for Performance Marketing | (Limited Availability) You can now integrate GenStudio for Performance Marketing email experiences with Journey Optimizer B2B Edition to enhance marketing efficiency and maintain brand consistency. With this integration, you can combine the GenStudio AI-powered content creation with the advanced orchestration capabilities in Journey Optimizer B2B Edition. [Learn more](../content/genstudio-email-workflow.md) |
| Feature | Spam detection reporting | To avoid spam filters and ensure that messages are delivered to audience inboxes, you can generate a _Spam report_ directly in the email design space. [Learn more](../content/email-spam-report.md) |
| Feature | Person details page | You can now click a person's name when it is displayed (as a hyperlink) in the Intelligent Dashboard, buying group details page, and account details page. This action opens the associated person details page, which information for the contact, their activity, and top-engaged buying groups. [Learn more](../accounts/person-details.md)|
| Feature | Account and buying group actions | Take actions directly from account details and buying group details pages for timely and intentional engagement. <li>Use the _Send email_ action to send an approved Marketo Engage email to selected account contacts or buying group members. [Learn more](../accounts/account-details.md#send-emails) <li>From the buying group details, actions also include _Assign a new member_, _Remove a member_, and _Edit a role_. [Learn more](../buying-groups/buying-group-details.md#members-tab) |
| Feature | In-CRM access to detail pages | You can now configure direct links to Journey Optimizer B2B Edition detail pages for accounts, contacts, and leads in your Customer Relationship Management (CRM) tool, such as Salesforce or Microsoft Dynamics. [Learn more](../accounts/crm-linking.md) |
| Feature | Custom CSS support for content design | You can now add your own custom CSS when you are authoring email and landing page content in the design space. [Learn more](../content/design-custom-css.md) |
| Feature| Intent keyword mapping configuration | To activate and manage the Intent Detection model, you can now upload a spreadsheet to define an intent data mapping category. [Learn more](../admin/intent-data.md) |
| Enhancement | Simulate Content from email summary | You can now access the _Simulate Content_ tools from the email summary (details and properties) when you open an email from the Emails list. This access is in addition to the email design space. [Learn more](../content/email-simulate-content.md#display-the-email-preview) |
| Enhancement | Total count display for roles templates list | The _[!UICONTROL Roles templates]_ list page is enhanced with the display of the total count next to the search bar. |

<!-- The following capabilities are currently available only for a set of program participants (Beta):

**Brand Kit with AI Assistant** - Maintain brand consistency across email assets by storing and managing brand assets. Add assets, such as colors, fonts, logos, themes, visual content, and compliance guidelines, and use them for your generative AI content creation. -->

## 2025.5 release notes

**Deployment date**: June 3, 2025

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | Email testing with Litmus | With a [Litmus Enterprise account](https://www.litmus.com/email-testing){target="_blank"}, you can now preview your email rendering in popular email clients from Journey Optimizer B2B Edition. This integration helps you to ensure that your email content looks great and works as designed in every email inbox. [Learn more](../content/email-test-rendering.md) |
| Enhancement | Duplicate email | When adding an email for a journey node, you can now duplicate an existing email. Modify the setting or content for the duplicated email, or leave it intact.  [Learn more](../content/add-email.md#add-an-email-to-your-journey) |
| Enhancement | Handlebar token format for email| Personalization tokens for email content now use an updated format that is fully compatible with Handlebar scripting. This format uses _camel case_ or underscores, eliminating spaces. [Learn more](../content/email-authoring.md#content-authoring---personalization) |
| Enhancement | Total count display for lists | The _[!UICONTROL Solution Interests]_ and _[!UICONTROL Account Journeys]_ list pages are enhanced with the display of the total count next to the search bar. |

## 2025.4 release notes

**Deployment date**: April 29, 2025

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | Account lists | You can now create a static or dynamic account list to target named accounts by your defined criteria, such as industry, location, or size of the company. <a href="../accounts/account-lists.md">Learn more</a> |
| Feature | Account list journey orchestration | Use journey action nodes to add and remove accounts for static account lists. <a href="../accounts/account-lists-journeys.md#take-an-action-node---add-to-account">Learn more</a> |
| Enhancement | Filter journey membership in Marketo Engage | Use Adobe Journey Optimizer B2B Edition account lists for the journey audience and then use the _Member of an account list_ filter in Marketo Engage smart lists. <a href="../accounts/account-lists-journeys.md#marketo-engage-program---member-of-account-list">Learn more</a> |
| Feature | Inactivity filters | Orchestrate journeys based on inactivity within Marketo Engage campaigns and programs, including email inactivity, interesting moments, data value changes, and visited web pages. <a href="../journeys/split-merge-paths-nodes.md#activity-filtering">Learn more</a> |
| Enhancement | Visited web page filter | Orchestrate journeys based on activity for visited web pages associated with Marketo Engage campaigns and programs. <a href="../journeys/split-merge-paths-nodes.md#people-path-conditions">Learn more</a> |
| Enhancement | Emails list | View a global list of active and draft emails to search, review, and update them across the associated account journeys. <a href="../content/emails-list.md">Learn more</a> |

## 2025.3 release notes

**Deployment date**: April 1, 2025

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | Duplicate account journeys | A duplicate action is now available for account journeys. You can duplicate the details for the account journey, or just a simple skeleton of the flow and path structure. <a href="../journeys/journey-overview.md#duplicate-journey">Learn more</a> |
| Feature | My Tokens for account journeys | You can now define a set of custom tokens with values that are specific to the account journey. This set of custom tokens is called _My Tokens_ and any of these custom tokens are for personalization when authoring journey emails. <a href="../content/personalization-my-tokens.md">Learn more</a> |
| Feature | Delete buying group stages | You can delete the buying group stages model when it is in a draft or published state. If it is published (live), you can delete it only when it is not associated with a solution interest. <a href="../buying-groups/buying-group-stages.md#delete-the-buying-group-stages-model">Learn more</a> |
| Enhancement | Journey node counts | Improved visibility into published journey membership counts at the node level. In the _Journey map_, nodes display _[!UICONTROL Total accounts entered]_. When you select and action node, the details on the right also include _[!UICONTROL Accounts not yet actioned on]_. And details for _Listen for an event_ nodes include _[!UICONTROL Accounts at this step]_. Use this information to validate account progression in your live, finished, and aborted journeys. |

## 2025.2 release notes

**Deployment date**: March 11, 2025

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | Customizable fields - content fragments | During visual fragment design, you can designate parameters for a component in the fragment as editable. This feature allows the email or template author to specify a custom field value that is specific to their needs. This customization flag is limited to image, text, and button visual components. <a href="../content/fragment-authoring.md#enable-fragment-customization">Learn more</a> |
| Feature | Journey duplication types | When you duplicate an account journey, you can include node details, excluding emails and SMS messages created in Journey Optimizer B2B Edition. As an alternative, you can create a skeleton copy of the structure and path flows, without node details and settings. <a href="../journeys/journey-overview.md#duplicate-journey">Learn more</a> | 
| Enhancement | Four additional sample email templates | The sample email templates library now includes four SecurFinacial templates as examples for reengagement, inform, nurture, and feedback content examples |

<!-- | Feature | B2B built-in roles and product permissions | Experience Platform now includes a set of built-in (default) roles that you can use to manage access to the B2B product capabilities. <a href="../admin/user-management.md#b2b-built-in-roles">Learn more</a> <br/>Administrators can now define custom roles in Adobe Experience Platform to include Journey Optimizer B2B Edition product permissions.  <a href="../admin/user-management.md#b2b-product-permissions">Learn more</a> | -->

## 2025.1 release notes {#Jan-2025}

**Deployment date**: February 6, 2025

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | Experience Event forwarding | Administrators can configure Adobe Experience Platform (AEP)-based event definitions. These configurations enable Marketers to create account journeys that react to AEP Experience Events.  <a href="../admin/configure-aep-events.md">Learn more</a> |
| Feature | Paid media destinations | Qualify known people for paid media campaigns from an account journey so that you can further engage them on advertising platforms, such as LinkedIn. Use a split path node in an account journey to segment account audiences based on specific behavior and identify accounts that warrant additional engagement. Then, add people from those accounts to an external customer audience through Real-time CDP to a supported paid media destination. <a href="../journeys/action-nodes.md#journey-optimizer-b2b-actions">Learn more</a> |
| Feature | Intelligent dashboard | View the progression of buying groups through their account journeys, including AI-generated insights for more intelligent analysis and accurate account prioritization. <a href="../dashboards/intelligent-dashboard.md">Learn more</a>|
| Feature | Buying group and account details | View insights at the buying group and account-level to have more context and historical data when you start engaging with a customer.<p>The buying group details include any first-party intent that is detected. <a href="../buying-groups/buying-group-details.md">Learn more</a><p>The account details accounts highlight the surge in engagement detected intent, so that you can alert sales on accounts that are ready for customized sales focused engagement.  <a href="../accounts/account-details.md">Learn more</a>|
| Feature | Journeys overview | When you access account journeys, the Overview tab provides a comprehensive snapshot of your active account journeys, detailing account progress using circle and bar charts that categorize and quantify completions, and engagement activities.  <a href="../dashboards/journeys-dashboard.md">Learn more</a>|
| Feature | Adobe Express image editing | Adobe Express Quick Actions allow you to make simple edits (such as cropping and resizing) to images for a more polished look in your content. <a href="../content/image-edit-adobe-express.md#quick-actions-in-adobe-express">Learn more</a>  <p>For a more comprehensive set of design tools, this integration enables a full Adobe Express license into Journey Optimizer B2B Edition. With this setup, the complete Adobe Express user interface becomes accessible within the local asset workspace. <a href="../content/image-edit-adobe-express.md#adobe-express-enterprise-license">Learn more</a> |
| Feature | Intent filters for buying group roles | When you submit your intent keywords, the Intent Detection model predicts a solution/product of interest with high enough confidence based on a lead's activity. <a href="../admin/intent-data.md">Learn more</a> <p>This intent data is available for defining buying group role conditions <a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">Learn more</a> |
| Enhancement | Marketo Engage event support in journeys | The _Listen for Event_ journey node now support two Marketo Engage events at the people level: _Visits web page_ and _Fills out form_. <a href="../journeys/listen-for-event-nodes.md#listen-for-marketo-engage-event">Learn more</a>|
| Enhancement | Buying group filters for Marketo Engage smart lists | View and create smart lists with buying group filters in Marketo Engage. These added filters allow you to suppress and include buying group members across Marketo Engage campaigns and programs from account journeys within Journey Optimizer B2B Edition. <a href="../buying-groups/marketo-engage-smart-list-buying-group-filters.md">Learn more</a>|
| Enhancement | Marketo Engage list membership filter for journeys and roles | In Journey Optimizer B2B, check for Marketo Engage list membership as a condition for a _split path by people_ node to help eliminate duplication in journey activities. <a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">Learn more</a> <p> For buying group roles templates, use list membership as a role condition. <a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">Learn more</a>|
| Enhancement | Engagement overview dashboard | This dashboard is updated to provide a comprehensive view of engagement. It showcases real-time metrics of account and individual interactions through snapshot circle charts and trend-revealing line charts over time. <a href="../dashboards/engagement-dashboard.md">Learn more</a>|

## 2024 releases

Expand the following lists for the features and enhancements for Journey Optimizer B2B Edition released in 2024.

+++October 2024 release notes

**Deployment date**: October 29, 2024

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | Conditional content in emails | Personalize your email content based on the recipient behavioral and profile characteristics – both at the account and lead level. <p>As you author an email for your account journey in the email visual design space, use conditional rules to define multiple variants for any content component. <a href="../content/conditional-content.md">Learn more</a> |
| Feature | _Add to List_ and _Remove from list_ people actions in journeys | Personalize your email content based on the recipient behavioral and profile characteristics – both at the account and lead level. <a href="../journeys/action-nodes.md">Learn more</a> |
| Feature | Content governance and component locking | To ensure adherence to approved content designs, use content governance features to lock email template content components. With content governance activated in the email template, marketers can alter only the permitted elements to keep it aligned with the content strategy. <a href="../content/template-content-governance.md">Learn more</a>|
| Feature | Buying group stages | When you define and publish a custom buying groups staging model, you can track buying group progression through the buying group lifecycle stages. Use these stages for identifying the next best actions for buying group members. You configure the transition rules and journey nodes that determine the stage progression and trigger actions based on changes. <a href="../buying-groups/buying-group-stages.md">Learn more</a> |
| Enhancement | New out-of-the-box email templates | The sample templates library now includes additional email templates designed for B2B marketers. Use these sample templates as a starting point and add your own branding and messaging. <a href="../content/email-templates.md#select-a-design-template">Learn more</a> |
| Enhancement | Custom fields as person attributes | If you have custom person fields defined in the account audience schema in Experience Platform, these fields are also available to use as person attributes in conditions. Use these custom attributes in: <li>Roles templates <a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">Learn more</a></li><li>Split paths by people journey nodes <a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">Learn more</a></li> |
| Enhancement | Email channel settings | Email settings are now visible in the Journey Optimizer B2B Edition interface. You can quickly review the current configurations and administrators can click _[!UICONTROL Edit settings]_ to go directly to the settings in Marketo Engage and update them according to the requirements of your organization. <a href="../admin/configure-channels-emails.md">Learn more</a> |

+++

+++September 2024 release notes

**Deployment date**: October 7, 2024

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Enhancement | Central assets library | The enhanced _central assets library_ allows you to use all image assets in your Marketo Engage instance, across Design Studio workspaces. There are built-in guardrails that prevent edits to the Marketo Engage assets from Journey Optimizer B2B Edition, as well as delete and move operations. These protections ensure that the source assets (Marketo Engage Design Studio) are maintained while allowing seamless read and reuse in Journey Optimizer B2B Edition.<p>For assets that are exclusively for use in Journey Optimizer B2B Edition, a specific workspace provides full asset management functions. <a href="../content/marketo-engage-design-studio.md">Learn more</a> |
| Feature | Recently accessed assets | The home page in the Journey Optimizer B2B Edition app now includes the _[!UICONTROL Recently accessed]_ section, which provides a list of the most recently accessed assets for the marketer or administrator. You can use this list to go directly to the asset that you recently worked on without navigating through a series of asset pages and searching. <p>The list provides additional information regarding the modification so that you can make the decision about which of the assets needs further modification from the last session. For email assets, it displays the account journey where the email asset is used. <a href="../home-page.md">Learn more</a> |
| Enhancement | Journey split node - reorder paths | In split path nodes, the path filtering is evaluated in top-down order. Each person or account proceeds along the first path that matches. You can reorder the defined paths by clicking the up and down arrows at the top right of each path card to move it higher or lower in the list. <a href="../journeys/split-merge-paths-nodes.md#split-paths">Learn more</a> |
| Enhancement | Journey split node - Additional activity history condition attributes | When using conditions to define the path filtering for a split node by people, there are two additional attributes: _Opened email_ and _Was delivered email_. These additions provide greater flexibility for filtering people in journey based on email activity. <a href="../journeys/journey-nodes.md#split-paths">Learn more</a> |

+++

+++August 2024 release notes

**Deployment date**: August 29, 2024

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Feature | LinkedIn Account Matched Audiences | Generate LinkedIn Ad audiences through Account Matched Audiences to help you fill empty roles in your buying groups. By defining a set of buying group filters, you can maintain a LinkedIn Matched Audience to target prospects who match your buying group parameters. <p>This feature leverages Experience Platform Destinations to manage some aspects of the integration. <a href="../data/linkedin-account-matched-audiences.md">Learn more</a> |
| Enhancement | Status lifecycle for visual content fragments | Visual fragments are now managed using a status lifecycle. The fragment status determines its availability for use in an email or email template, and the changes that you can make to it. <p>This enhanced workflow makes it easy to manage reused content according to your promotional and communications calendar. <a href="../content/fragments.md#fragment-status-and-lifecycle">Learn more</a> |

+++
