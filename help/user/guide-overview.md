---
title: Adobe Journey Optimizer B2B Edition Documentation
description: Complete documentation for Journey Optimizer B2B Edition - explore the available resources for onboarding, creating buying groups, building account journeys, and managing content.
exl-id: 3d7b6c82-95c3-4d89-b3dc-7fd5b0aef615
---
# Adobe Journey Optimizer B2B Edition Documentation

[!DNL Adobe Journey Optimizer B2B Edition] is a first-of-its-kind application that lets marketing and sales teams orchestrate account-based experiences and qualify buying groups for specific products across the entire customer lifecycle. It uses AI to engage and qualify buying groups within target accounts, helping your teams to generate a higher quality pipeline, design better acquisition, expansion, and retention strategies. It also enables shared insights across sales and marketing teams. 

This documentation provides information for mastering the application. It is designed for marketers, business development representatives, data analysts, and operational administrators.

## What's new

Review this sampling of the latest additions and enhancements in the [!DNL Journey Optimizer B2B Edition] application and documentation. 

>[!BEGINTABS]

>[!TAB AI agents]

With the [Experience Platform Agent Orchestrator](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/home#agent-orchestrator){target="_blank"}, the AI Assistant interface can automatically call upon specialized agents to get you the right answers and insights. Agent Orchestrator remembers your conversation history, enabling you to build on previous questions naturally without repeating context, and combines insights from multiple agents to present you with clear, unified responses. In the [!DNL Journey Optimizer B2B Edition] context, there are three purpose-built agents for specific B2B tasks and domains:

* [Audience Agent B2B](./agents/audience-agent-b2b.md)
* [Journey Agent B2B](./agents/journey-agent.md)
* [Account Qualification Agent](./agents/sales-qualifier.md#account-qualification-agent)

>[!TAB WhatsApp channel]

When developers and product administrators configure an integration with a Meta Business Manager account, marketers can include WhatsApp messages as a content channel in account journeys using the Meta Cloud API. WhatsApp joins email and SMS as an available channel for delivering journey content directly to account members.

[!BADGE Learn more]{type=Informative url="/help/user/admin/configure-channels-whatsapp.md" tooltip="Learn about the WhatsApp channel"}

>[!TAB Generative AI models]

Email designers can now select from standard [!DNL Firefly] models, custom [!DNL Firefly] models trained on brand-specific assets, and approved third-party image models when generating images for email content. This selection gives teams control over which model fits their specific design scenario, from general content needs to branded or specialized use cases.

[!BADGE Learn more]{type=Informative url="/help/user/content/generative-ai-models.md" tooltip="Learn about generative AI model selection"}

>[!TAB Send-time optimization]

For _Send email_ action nodes in person journeys, you can now use send-time optimization to personalize email delivery timing. The system predicts when each person is most likely to engage and schedules delivery accordingly, rather than sending to all recipients at the same time.

[!BADGE Learn more]{type=Informative url="/help/user/content/email-send-time-optimization.md" tooltip="Learn about send-time optimization"}

>[!TAB Journey re-entry]

You can now send accounts/people through an account journey workflow multiple times. Re-entry addresses multiple scenarios, such as re-evaluation of qualification criteria and re-usable nurture workflows. Use the re-entry settings to set criteria, limits, and wait times so that accounts requalify for the journey in a controlled way.

[!BADGE Learn more]{type=Informative url="/help/user/journeys/journey-re-entry.md" tooltip="Learn about journey re-entry"}

>[!TAB Brand themes]

With themes, non-technical designers have the ability to create reusable email content design guidelines that align to a specific brand and styling. Themes empower marketers to leverage visually appealing, brand-consistent emails faster and with less effort, and provide advanced customization options for unique design needs.

[!BADGE Learn more]{type=Informative url="/help/user/content/brand-themes.md" tooltip="Learn about brand themes"}

>[!TAB Persona mapping]

Marketers can define detailed profiles, including background, responsibilities, pain points, and preferred communication channels. With these definitions, administrators can configure personas according to person attributes in [!DNL Journey Optimizer B2B Edition] so that role templates can use streamlined and consistent role conditions that capture these personas.

[!BADGE Learn more]{type=Informative url="/help/user/admin/persona-mapping.md" tooltip="Learn about persona mapping"}

>[!ENDTABS]

## Start exploring {#section-explore}

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

Latest Release Notes

Stay updated with the latest release notes, new features, and improvements in Adobe Journey Optimizer B2B Edition.

[View Release Notes](./release-notes/release-notes.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

Get Started

Review the Journey Optimizer B2B Edition onboarding guidance for administrators and marketers.

[Administrators](./setup-ultimate.md)
[Users](./start/get-started.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

Configure Your XDM fields

Implement the system configurations to activate the XDM schemas and fields that you want to use in Adobe Journey Optimizer B2B Edition.

[View XDM field management](./admin/xdm-field-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

Communication Channels

Configure and manage email, SMS, WhatsApp, and other channels for personalized customer interactions.

[Configure email channel](./admin/configure-channels-emails.md)
[Configure SMS channel](./admin/configure-channels-sms.md)
[Configure WhatsApp channel](./admin/configure-channels-whatsapp.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

Create a Journey

Design, orchestrate, manage, and optimize personalized journeys.

[Explore Journeys](./journeys/journeys-overview.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/users.svg)

Understand Buying Groups

Detailed guidance on creating, managing, and optimizing buying groups for effective targeting.

[Learn about buying groups](./buying-groups/buying-groups-overview.md)
:::

::::

<!--
:::
![icon](https://cdn.experienceleague.adobe.com/icons/image.svg)

Design Content

Learn how to author and manage content for personalized customer experiences orchestrated through journeys.

[Explore Content Components](./content/content-components.md)
::: 
-->

## Overview demo

Discover the components of a buying group and understand the basics of building an account journey.

>[!VIDEO](https://video.tv.adobe.com/v/3432054?quality=12) 

## Explore the documentation

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="../assets/do-not-localize/icon-quick-start.svg" width="35px" alt="Get started"><br/>
      <strong>Get started</strong><br/><a href="home-page.md">Login and home page</a><br/><a href="./start/get-started.md">Onboarding guidance</a> <br/><a href="./ai-assistant/ai-assistant-overview.md">AI Assistant</a>
    </td>
    <!--
    <td>
      <img src="../assets/do-not-localize/icon-configure.svg" width="35px"><br/>
      <strong>Configuration<br/>administration</strong><br/><a href="using/configuration/channel-surfaces.md">Channel surfaces</a> - <a href="using/configuration/about-data-sources-events-actions.md">Configure journeys</a>  - <a href="using/administration/permissions-overview.md">Access control</a> - <a href="using/administration/sandboxes.md">Sandboxes management</a>
    </td>
    -->
    <td>
      <img src="../assets/do-not-localize/icon_audience.svg" width="35px" alt="Buying groups"><br/>
      <strong>Buying groups</strong><br/><a href="./buying-groups/buying-groups-overview.md">Buying groups overview</a><br/><a href="./buying-groups/buying-groups-role-templates.md">Role templates</a><br/><a href="./buying-groups/solution-interests.md">Solution interests</a><br/><a href="./buying-groups/buying-groups-create.md">Create buying groups</a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-paths.svg" width="35px" alt="Account journeys"><br/>
      <strong>Account journeys</strong><br/><a href="./journeys/journeys-overview.md">Journeys overview</a><br/><a href="./journeys/create-publish-journey.md#create-a-journey">Create an account journey</a><br/><a href="./journeys/journey-nodes.md">Journey nodes</a>
    </td>
  </tr>
  <tr style="border: 0;">
    <td>
      <img src="../assets/do-not-localize/icon-campaign.svg" width="35px" alt="Journey content"><br/>
      <strong>Journey content</strong><br/><a href="./content/add-email.md">Email channel</a><br/><a href="./content/ai-assistant-emails.md">AI Assistant for email</a><br/><a href="./content/genstudio-email-workflow.md">GenStudio email experiences</a><br/><a href="./content/sales-alert-email.md">Sales alert email</a><br/><a href="./content/sms-authoring.md">SMS channel</a>
    </td>
        <td>
      <img src="../assets/do-not-localize/icon_assets.svg" width="35px" alt="Content management"><br/>
      <strong>Content management</strong><br/><a href="./content/assets-overview.md">Assets overview</a><br/><a href="./content/email-templates.md">Email templates</a><br/><a href="./content/fragments.md">Visual fragments</a><br/><a href="./content/conditional-content.md">Conditional content</a><br/><a href="./content/brand-themes.md">Brand themes</a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-offer.svg" width="35px" alt="Insights and dashboards"><br/>
      <strong>Insights</strong><br/><a href="./dashboards/intelligent-dashboard.md">Intelligent dashboard</a><br/><a href="./dashboards/engagement-dashboard.md">Engagement dashboard</a><br/><a href="./dashboards/buying-groups-dashboard.md">Buying groups dashboard</a><br/><a href="./dashboards/journeys-dashboard.md">Journeys dashboard</a><br/><a href="./buying-groups/incrm-insights.md">In-CRM Insights</a>
    </td>

  </tr>
</table>

## Additional resources

<table style="table-layout:fixed">
<tr><td><strong>Adobe Journey Optimizer B2B Edition</strong><br/>
<a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b-learn/tutorials/overview" target="_blank">Videos and tutorials</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html" target="_blank">Product description</a> <!-- - <a href="https://www.adobe.com/content/dam/cc/en/security/pdfs/AJO_SecurityOverview.pdf" target="_blank">Security overview (PDF)</a> - <a href="https://developer.adobe.com/journey-optimizer-apis/" target="_blank">APIs reference</a> - <a href="https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html" target="_blank">Journey Optimizer Schema Dictionary</a> -->
</td>
<td><strong>Adobe Experience Platform</strong><br/>
<a href="https://experienceleague.adobe.com/en/docs/experience-platform/landing/home" target="_blank">Documentation</a> - <a href="https://business.adobe.com/products/experience-platform/documentation-and-developer-resources.html" target="_blank">Developer resources</a>
</td></tr>
<tr><td><strong>Adobe Real-Time Customer Data Platform</strong><br/>
<a href="https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home" target="_blank">Documentation</a> - <a href="https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/overview" target="_blank">Developer tutorials</a>
</td><td><strong>Adobe Marketo Engage</strong><br/>
<a href="https://experienceleague.adobe.com/en/docs/marketo/using/home" target="_blank">User documentation</a> - <a href="https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/home" target="_blank">Developer documentation</a>
</td>
</tr></table>

