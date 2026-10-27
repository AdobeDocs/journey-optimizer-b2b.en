---
title: AI Capabilities in Journey Optimizer B2B Edition
description: Accelerate workflows with AI capabilities - get product knowledge, troubleshooting help, and operational insights for Journey Optimizer B2B Edition.
feature: AI Assistant
role: User, Admin
level: Beginner
exl-id: 52ff66d2-1969-4e2c-985a-c75e613368de
autotag-review: '2026-06-05T16:05:30.499Z'
TQID: 'https://experienceleague.adobe.com/4bXkOzwadjZVzhedVO6oQEEV1biaWMZFHEuqey74qek'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
subfeature_v2:
  - id: eb7448d0-50e6-41cc-83e2-a84cd2413491
    internal-label: Operational Insights
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# AI capabilities in Journey Optimizer B2B Edition

Use AI capabilities in [!DNL Adobe Journey Optimizer B2B Edition] to generate content, explore product knowledge, and gain operational insights.

>[!IMPORTANT]
>
>An agreement to the [user guidelines](https://www.adobe.com/legal/licenses-terms/adobe-gen-ai-user-guidelines.html){target="_blank"} is required before you can use AI capabilities in [!DNL Journey Optimizer B2B Edition]. This agreement also contains the public beta agreement so that you can use additional AI-enabled features as they roll out.

+++View the user agreement interface

![The first page of the user agreement.](./assets/user-agreement-1.png)

![The last page of the user agreement.](./assets/user-agreement-2.png)

+++

## Use the [!DNL Coworker] app {#coworker-app}

Use the [!DNL CX Enterprise Coworker] app interface for all chat workflows other than generating content. Ask product questions, explore operational insights, and use [journey skills](../agents/journey-agent.md) and [audience skills for B2B accounts and people](../agents/audience-agent-b2b.md). Content generation remains available within [!DNL Journey Optimizer B2B Edition].

For instructions on opening the app, starting conversations, and using chat features, see the [CX Coworker interface guide](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}.

Consider which type of inquiry you need before you submit an [!DNL Coworker] chat query.

### Product knowledge

Product knowledge refers to concepts and topics grounded in the [!DNL Journey Optimizer B2B Edition] documentation on [!DNL Adobe Experience League]. Product knowledge questions can be further specified into the following sub-groups:

| Product knowledge | Examples |
| --- | --- |
| Pointed learning | <li>What is a buying group? <li> Show me an example of a buying group roles template? |
| Open discovery | <li>What are the steps to create buying groups? <li>How do I use custom fields in a buying group roles templates? |
| Troubleshooting | <li>Why weren't buying Groups for my journey created? <li>Why can't I find Experience Events to listen to in the journey? |

### Operational insights

_Operational insights_ refer to answers that [!DNL Coworker] generates about your metadata objects (attributes, account audiences, dataflows, datasets, destinations, account journeys, schemas, sources, buying group templates, and solution interests). These insights include counts, lookups, and lineage impact. They do not look at any data within the sandbox.

* Which account audience has the largest audience size and what is that size?
* How many account audiences have never been used in any journeys?
* What active journeys use solution interest _x_?

You can ask [!DNL Coworker] questions about your operational insights in the following domains:

| Domain | Supported metadata | Unsupported metadata |
| --- | --- | --- |
| Attributes/fields | <li>Attribute name search <li>Attribute - schema relationship <li>Attribute - dataset relationship <li>Attribute - audience relationship <li>Attribute - destination relationship | <li>Attribute class <li>Audit <li>Deprecation status <li>Labels <li>Value stored in attributes |
| Account Audiences <br><br>**_Note:_** In the [!DNL Journey Optimizer B2B Edition] context, [!DNL Coworker] chat can only answer audience questions for Account Audiences. In the [!DNL Adobe Experience Platform] context, [!DNL Coworker] chat can answer questions only for Person Audiences. | <li>Audience count <li>Audience type (streaming or batch) <li>Creation/modification dates <li>Activation status <li>Member count <li>Duplicate audiences <li>Name and ID search | <li>Audience overlaps <li>Audience activation <li>Audit <li>Create/modification <li>Labels <li>Member qualification trends |
| Dataflows | <li>Dataflow counts <li>Dataflow status <li>Dataflow - dataset relationship <li>Dataflow - source relationship | <li>Creation/modification <li>Dataflow-batch relationships <li>Ingest profile count |
| Datasets | <li>Dataset count <li>Profile enable status <li>Creation/modification date <li>Dataset - schema relationship <li>Dataset - audience relationship <li>Dataset - attribute relationship <li>Dataset - dataflow relationship <li>Name search <li>Name and ID search | <li>Audit <li>Created by <li>Dataset - batch relationship <li>Dataset creation/modification <li>Dataset size <li>Number of profiles <li>Number of rows <li>Value search |
| Destinations | <li>Configured destination counts <li>Destination - audience relationship <li>Destination attribute relationship | <li>Account setup <li>Account credential information <li>Unique profiles activated |
| Journeys (Account Journeys) | <li>Count <li>Name and ID search <li>Journey status <li>Creation/modification dates | <li>Attributes - journey relationships <li>Audit <li>Creation/modification <li>Created by |
| Schemas | <li>Schema counts <li>Creation/modification date <li>Schema - attribute relationship <li>Schema - dataset relationship <li>Schema - audience relationship <li>Profile enable status <li>Name search <li>Name and ID search | <li>Audit <li>Creation/modification <li>Created by <li>Field groups <li>Identities <li>Identity namespaces <li>Labels <li>Number of profiles |
| Sources | <li>Account counts <li>Account status <li>Active/inactive dataflows for each account <li>Source connector - dataflow relationship <li>Source account - dataflow relationship | <li>Account credentials information <li>Account set upData ingestion metrics <li>Number of profilesSource - batch relationships |
| Buying Group Template | <li>Counts <li>Status <li>Roles <li>Name and ID search | <li>Role rules |
| Solution Interest | <li>Counts <li>Status <li>Solution Interest - Buying Group Template relationship <li>Name and ID search | <li>Solution Interest - Buying Group relationship |

{style="table-layout:fixed"}

For operational insights questions, answers may not reflect the current state of the UI. The data that backs these questions is updated once every 24 hours. For example, changes that users make in [!DNL Adobe Real-Time Customer Data Platform] during the daytime are synced with the data stores at night, and then they become available for user questions in the morning. To inquire about specific data related to objects, sign in to a sandbox.

### Privacy, security, and governance

[!DNL Coworker] chat in [!DNL Journey Optimizer B2B Edition] prioritizes privacy, security, and governance. Review the following information to learn about the customer trust-focused capabilities that you can expect from [!DNL Coworker] chat:

* [!DNL Coworker] does not use personal data today, even for training purposes.

* You can view a 30-day log of your previous interactions with [!DNL Coworker] chat.

* [!DNL Coworker] is grounded in sandbox-specific data and public Adobe documentation when responding to prompts. Data is not shared across sandboxes.

* Prompts that you provide to [!DNL Coworker] chat are not shared to other customers.

## Next steps

With a general understanding of [!DNL Coworker] chat, proceed to enable and use it during your workflows. Refer to the following documentation for more information:

* [Enable AI capabilities access](./enable-ai-access.md)
* [Question guidance](./question-guidance.md)
* [CX Coworker interface guide](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}
