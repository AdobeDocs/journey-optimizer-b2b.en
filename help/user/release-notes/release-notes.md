---
title: Release notes
description: Latest release notes for Adobe Journey Optimizer B2B edition
exl-id: 7d3f1c26-d8a6-4065-a70f-5b30cb975dc8
---
# Journey Optimizer B2B Edition release notes

Adobe Journey Optimizer B2B Edition continuously delivers new features, enhancements to existing features, and bug fixes.

Journey Optimizer B2B Edition is built natively on [!DNL Adobe Experience Platform] and inherits from its latest innovations and improvements. Learn more about these changes in [Adobe Experience Platform Release Notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/latest){target="_blank"}.

Review the [product description](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} for information about entitlements, performance guardrails, and limitations.

## October 2024 release notes {#Oct-2024}

**Release date**: October 29, 2024

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| New feature | Conditional content in email templates| Personalize your email content based on the recipient behavioral and profile characteristics – both at the account and lead level. <p>As you author an email for your account journey in the email designer, use conditional rules to define multiple variants for any content component. <a href="../content/conditional-content.md">Learn more</a> |
| New feature | _Add to List_ and _Remove from list_ people actions in journeys | Personalize your email content based on the recipient behavioral and profile characteristics – both at the account and lead level. <a href="../journeys/journey-nodes.md#action-nodes">Learn more</a> |
| New feature | Content governance and component locking | To ensure adherence to approved content designs, use content governance features to lock email template content components. With content governance activated in the email template, marketers can alter only the permitted elements to keep it aligned with the content strategy. <a href="../content/template-content-governance.md">Learn more</a>|
| New feature | Buying group stages | When you define and publish a custom buying groups staging model, you can track buying group progression through the buying group lifecycle stages. Use these stages for identifying the next best actions for buying group members. You configure the transition rules and journey nodes that determine the stage progression and trigger actions based on changes. <a href="../buying-groups/buying-group-stages.md">Learn more</a> |
| Enhancement | New out-of-the-box email templates | The sample templates library now includes additional email templates designed for B2B marketers. Use these sample templates as a starting point and add your own branding and messaging. <a href="../content/email-templates.md#select-a-design-template">Learn more</a> |
| Enhancement | Custom fields as person attributes | If you have custom person fields defined in the account audience schema in Experience Platform, these fields are also available to use as person attributes in conditions. Use these custom attributes in: <li>Roles templates <a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">Learn more</a></li><li>Split paths by people journey nodes <a href="../journeys/journey-nodes.md#add-a-split-path-by-people-node">Learn more</a></li> |
| Enhancement | Email channel settings | Email settings are now visible in the Journey Optimizer B2B Edition interface. You can quickly review the current configurations and administrators can click _[!UICONTROL Edit settings]_ to go directly to the settings in Marketo Engage and update them according to the requirements of your organization. <a href="../admin/configure-channels-emails.md">Learn more</a> |

## September 2024 release notes {#Sept-2024}

**Release date**: October 7, 2024

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| Enhancement | Central assets library | The enhanced _central assets library_ allows you to use all image assets in your Marketo Engage instance, across Design Studio workspaces. There are built-in guardrails that prevent edits to the Marketo Engage assets from Journey Optimizer B2B Edition, as well as delete and move operations. These protections ensure that the source assets (Marketo Engage Design Studio) are maintained while allowing seamless read and reuse in Journey Optimizer B2B Edition.<p>For assets that are exclusively for use in Journey Optimizer B2B Edition, a specific workspace provides full asset management functions. <a href="../content/marketo-engage-design-studio.md">Learn more</a> |
| New feature | Recently accessed assets | The home page in the Journey Optimizer B2B Edition app now includes the _[!UICONTROL Recently accessed]_ section, which provides a list of the most recently accessed assets for the marketer or administrator. You can use this list to go directly to the asset that you recently worked on without navigating through a series of asset pages and searching. <p>The list provides additional information regarding the modification so that you can make the decision about which of the assets needs further modification from the last session. For email assets, it displays the account journey where the email asset is used. <a href="../home-page.md">Learn more</a> |
| Enhancement | Journey split node - reorder paths | In split path nodes, the path filtering is evaluated in top-down order. Each person or account proceeds along the first path that matches. You can reorder the defined paths by clicking the up and down arrows at the top right of each path card to move it higher or lower in the list. <a href="../journeys/journey-nodes.md#split-paths">Learn more</a> |
| Enhancement | Journey split node - Additional activity history condition attributes | When using conditions to define the path filtering for a split node by people, there are two additional attributes: _Opened email_ and _Was delivered email_. These additions provide greater flexibility for filtering people in journey based on email activity. <a href="../journeys/journey-nodes.md#split-paths">Learn more</a> |

## August 2024 release notes {#Aug-2024}

**Release date**: August 29, 2024

This release includes the following new capabilities and enhancements:

| Type | Item | Description |
| ---- | ---- | ----------- |
| New feature | LinkedIn Account Matched Audiences | Generate LinkedIn Ad audiences through Account Matched Audiences to help you fill empty roles in your buying groups. By defining a set of buying group filters, you can maintain a LinkedIn Matched Audience to target prospects who match your buying group parameters. <p>This feature leverages Experience Platform Destinations to manage some aspects of the integration. <a href="../data/linkedin-account-matched-audiences.md">Learn more</a> |
| Enhancement | Status lifecycle for visual content fragments | Visual fragments are now managed using a status lifecycle. The fragment status determines its availability for use in an email or email template, and the changes that you can make to it. <p>This enhanced workflow makes it easy to manage reused content according to your promotional and communications calendar. <a href="../content/fragments.md#fragment-status-and-lifecycle">Learn more</a> |
