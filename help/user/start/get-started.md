---
title: Onboarding Guidance for Administrators and Marketers
description: As a new administrator or user in Journey Optimizer B2B Edition, learn about the key areas in the onboarding process.
role: Admin, User
level: Beginner
exl-id: 83f8e666-0b31-4323-9902-4fdf4446424c
---
# Onboarding guidance 

The features and tools that you want to tackle in Adobe Journey Optimizer B2B Edition depends on your role within your team. Based on your organization, administrators can define several types of users and grant them access to certain capabilities depending on their permissions.

>[!TIP]
>
>Also check your license entitlements and the corresponding [product description](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} about performance guardrails and static limitations.

>[!BEGINTABS]

>[!TAB Administrator]

Before your team can start using the Adobe Journey Optimizer B2B Edition features, several steps are required to prepare your environment. Perform these steps so that the data engineer and marketer can start working with Adobe Journey Optimizer B2B Edition.

As a system administrator, you need to understand product profiles and assign permissions for sandbox administration and channel configuration. You also need to set up sandboxes and manage them for the available product profiles. You can then assign team members to the product profiles. Product administrators that have access to the Adobe Admin Console can manage these capabilities. [Learn more about Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html).

Learn about access management in the following pages:

1. **Create sandboxes** to partition your instances into separate, isolated virtual environments. [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home#understanding-sandboxes){target="_blank"}

1. **Work with your data engineer** to plan and implement your B2B audience and profile activation. Review the published blueprints and follow the guidelines according to your requirements. [Learn more](https://experienceleague.adobe.com/en/docs/blueprints-learn/architecture/b2b-activation/overview){target="_blank"}

1. **Plan and implement the Marketo Engage integration** to incorporate custom schema, ingestion of profiles and accounts, and the orchestration of personalized journeys for buying groups. [Learn more](https://experienceleague.adobe.com/en/docs/blueprints-learn/architecture/b2b-activation/b2b-journeys-with-marketo){target="_blank"}

1. **Set up the product profile**. A product profile is a set of unitary rights in Adobe Experience Platform that allow users access to certain functionalities or objects in the interface. [Learn more](../admin/user-management.md#create-the-marketo-engage-product-profile)

1. **Set up user permissions** for product profiles, including sandboxes, and give access to your team members by assigning them to different product profiles. This task is performed in the Admin Console. [Learn more](../admin/user-management.md#create-a-user-group)

1. **Configure email delivery** in Marketo Engage, which enables your team to send email content from account journeys. [Learn more](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps#ensure-email-deliverability){target="_blank"}

1. **Configure SMS services**. Set up one of the supported third-party SMS providers who offer text messaging services independently and configure the account credentials in Adobe Journey Optimizer B2B Edition. [Learn more](../admin/configure-channels-sms.md)

1. **Configure and enable use of Adobe Experience Manager Assets** for teams that use Assets as a Cloud Service for centralized digital asset management. [Learn more](../admin/configure-aem-repositories.md)

1. **Set up Adobe Experience Platform (AEP) Experience Event definitions** for teams responsible for creating account journeys that listen to AEP Experience Events. [Learn more](../admin/configure-aep-events.md)

>[!TAB Marketer]

As a marketer, or an _Account Journey Practitioner_, you are responsible for designing journeys and crafting content. You can start working with Adobe Journey Optimizer B2B Edition after the system administrator and the data engineer prepare your environment and grant you access.

Refer to the following sections to set up your first journey, add assets, and send content:

1. **Add account audiences**. Journey Optimizer B2B Edition allows you to create account audiences through segment definitions directly from the application, and leverage them into your account journeys. [Learn more](../audiences/account-audience-overview.md)

1. **Create buying groups**. Define the key components for meeting your business goals and objectives, and create buying groups that identify the members for your target account lists. [Learn more](../buying-groups/buying-groups-overview.md)

1. **Create and manage assets**. Adobe Experience Manager Assets provides a single, centralized repository of assets that you can use to populate your messages. [Learn more](../content/assets-overview.md)

1. **Add personalizalized and dynamic email templates**. Leverage Journey Optimizer B2B Edition personalization and dynamic content capabilities to adapt your message to your audience. [Learn more](../content/email-templates.md)

1. **Design account journeys to deliver personalized, contextual experiences**. Journey Optimizer B2B Edition allows you to build real-time orchestration use cases with contextual data stored in events or data sources. Design multi-step, advanced scenarios powered by the following capabilities:

   * Send real-time unitary delivery triggered when an event is received, or in batch using Adobe Experience Platform audiences.

   * Use contextual data from events, information from Adobe Experience Platform, or data from third-party API services.

   * Use the built-in channel actions (email and SMS) to send messages designed in Journey Optimizer B2B Edition.

   * In the journey map, build your multi-step use cases, add conditions and send personalized messages.

   [Learn more](../journeys/journey-overview.md)

>[!ENDTABS]
