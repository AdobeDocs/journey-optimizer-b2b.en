---
title: AI Assistant in Journey Optimizer B2B Edition
description: Placeholder
feature: AI Assistant
level: Beginner
exl-id: 52ff66d2-1969-4e2c-985a-c75e613368de
---
# AI Assistant in Journey Optimizer B2B Edition

AI Assistant in Journey Optimizer B2B Edition is created from the same technology foundation of [AI Assistant in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/home){target="_blank"}. It is a conversational experience that you can use to accelerate your workflows in Adobe Journey Optimizer B2B Edition. You can use AI Assistant to gain more understanding of the product capabilities, troubleshoot problems, or search through information and find operational insights for Journey Optimizer B2B Edition. 
 
>[!IMPORTANT]
>
>An agreement to the [user guidelines](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html) is required before you can use AI Assistant in Journey Optimizer B2B Edition. This agreement also contains the public beta agreement so that you can use additional AI Assistant features as they roll out in a beta capacity.

+++View the user agreement interface

![The first page of the user agreement.](./assets/user-agreement-1.png)

![The last page of the user agreement.](./assets/user-agreement-2.png)

+++

## AI Assistant capabilities in Journey Optimizer B2B Edition

To formulate a response to your submitted questions, AI Assistant queries a database and translates data from the database into a human-readable answer. This response is an internal representation of underlying data, and is also known as the _**_Knowledge Graph_**_ -- a comprehensive web of concepts, data, and metadata for a given answer. The Knowledge Graph consists of sub-graphs that are referenced whenever queries are submitted:

* Experience League documentation.
* Operational artifacts, such as schemas, fields, audiences and journeys.

Consider which type of inquiry you need before you submit an AI Assistant query:

### Product knowledge

Product knowledge refers to concepts and topics grounded in the Journey Optimizer B2B Edition documentation on Adobe Experience League. Product knowledge questions can be further specified into the following sub-groups:

| Product knowledge | Examples |
| --- | --- |
| Pointed learning | <li>What is a buying group? <li> Show me an example of a buying group roles template? |
| Open discovery | <li>What are the steps to create buying groups? <li>How do I use custom fields in a buying group roles templates? |
| Troubleshooting | <li>Why weren't buying Groups for my journey created? <li>Why can't I find Experience Events to listen to in the journey? |

### Operational insights

_Operational insights_ refer to answers that AI Assistant generates about your meta data objects (attributes, account audiences, dataflows, datasets, destinations, account journeys, schemas, sources, buying group templates, and solution interests). These insights include counts, lookups, and lineage impact. They do not look at any data within the sandbox.

* Which account audience has the largest audience size and what is that size?
* How many account audiences have never been used in any journeys?
* What active journeys use solution interest _x_?

You can ask AI Assistant questions about your operational insights in the following domains:

| Domain | Supported metadata | Unsupported metadata |
| --- | --- | --- |
| Attributes/fields | <li>Attribute name search <li>Attribute - schema relationship <li>Attribute - dataset relationship <li>Attribute - audience relationship <li>Attribute - destination relationship | <li>Attribute class <li>Audit <li>Deprecation status <li>Labels <li>Value stored in attributes |
| Account Audiences <br><br>**_Note:_** AJO B2B AI Assistant can only answer audience questions for Account Audiences, while Experience Platform AI Assistant can answer questions only for Person Audiences | <li>Audience count <li>Audience type (streaming or batch) <li>Creation/modification dates <li>Activation status <li>Member count <li>Duplicate audiences <li>Name and ID search | <li>Audience overlaps <li>Audience activation <li>Audit <li>Create/modification <li>Labels <li>Member qualification trends |
| Dataflows | <li>Dataflow counts <li>Dataflow status <li>Dataflow - dataset relationship <li>Dataflow - source relationship | <li>Creation/modification <li>Dataflow-batch relationships <li>Ingest profile count |
| Datasets | <li>Dataset count <li>Profile enable status <li>Creation/modification date <li>Dataset - schema relationship <li>Dataset - audience relationship <li>Dataset - attribute relationship <li>Dataset - dataflow relationship <li>Name search <li>Name and ID search | <li>Audit <li>Created by <li>Dataset - batch relationship <li>Dataset creation/modification <li>Dataset size <li>Number of profiles <li>Number of rows <li>Value search |
| Destinations | <li>Configured destination counts <li>Destination - audience relationship <li>Destination attribute relationship | <li>Account setup <li>Account credential information <li>Unique profiles activated |
| Journeys (Account Journeys) | <li>Count <li>Name and ID search <li>Journey status <li>Creation/modification dates | <li>Attributes - journey relationships Audit <li>Creation/modification <li>Created by |
| Schemas | <li>Schema counts <li>Creation/modification date <li>Schema - attribute relationship <li>Schema - dataset relationship <li>Schema - audience relationship <li>Profile enable status <li>Name search <li>Name and ID search | <li>Audit <li>Creation/modification <li>Created by <li>Field groups <li>Identities <li>Identity namespaces <li>Labels <li>Number of profiles |
| Sources | <li>Account counts <li>Account status <li>Active/inactive dataflows for each account <li>Source connector - dataflow relationship <li>Source account - dataflow relationship | <li>Account credentials information <li>Account set upData ingestion metrics <li>Number of profilesSource - batch relationships |
| Buying Group Template | <li>Counts <li>Status <li>Roles <li>Name and ID search | <li>Role rules |
| Solution Interest | <li>Counts <li>Status <li>Solution Interest - Buying Group Template relationship <li>Name and ID search | <li>Solution Interest - Buying Group relationship |

{style="table-layout:fixed"}

For operational insights questions, answers may not reflect the current state of the UI. The data that backs these questions is updated once every 24 hours. For example, changes that users make in Real-Time CDP during the daytime are synced with the data stores at night, and then they become available for user questions in the morning. Log into a sandbox to inquire about specific data related to objects.

### Feature scope

Currently, the scope of AI Assistant is as follows:

* **Product knowledge**: AI Assistant can answer product knowledge questions for Real-Time Customer Data Platform and Adobe Journey Optimizer B2B Edition.

* **Operational insights**: You can ask AI Assistant questions for operational insights for the following data objects: attributes, account audiences, dataflows, datasets, destinations, account journeys, schemas, sources, buying group templates, and solution interests.

### Privacy, security, and governance

AI Assistant in Journey Optimizer B2B Edition is built with privacy, security, and governance at the forefront. Review the following information to learn about the customer trust-focused capabilities that you can expect from AI Assistant:

* No personal data is used by AI Assistant today, even for training purposes.

* AI Assistant is unaware of customer data, such as people, account, opportunities, and buying groups.

* You must have explicit permission to interact with AI Assistant. 

   * An administrator can set permissions using the [Permissions UI](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions){target="_blank"} and the [Admin Console](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/browse){target="_blank"}.

   * Permissions are granular and your sandbox administrator can configure which users are able to ask different question categories (product knowledge-based questions with AI Assistant or questions on operational insights).

* You can view a log of your previous interactions with AI Assistant with a 30-day retention policy.

* AI Assistant is grounded in sandbox-specific data and public Adobe documentation when answering to user prompts. Data is not shared across sandboxes.

* Prompts that you provide to AI Assistant are not shared to other customers.

### Frequently asked questions

The following is a list of answers to frequently asked questions about AI Assistant in Journey Optimizer B2B Edition.

**Is AI Assistant's information provided in real-time?**

   The data presented in AI Assistant responses is updated daily. This cycle means that the data included in responses can be up to 24 hours older than the data that is displayed in the user interface at the time of the response.

**What are the capabilities of AI Assistant?**

   AI Assistant can address Adobe product knowledge queries and can answer questions related to operational insights of your operational artifacts.

**Can AI Assistant provide information about customer data?**

   No. AI Assistant does not have access to customer data and therefore, it is not looked at or used by AI Assistant.

**Is my personal information used in AI Assistant's training data?**

   AI Assistant does not use personal information for training purposes. Do not provide any personal information about yourself (including your name or contact information) or any other parties to AI Assistant.

## Next steps

With a general understanding of AI Assistant, proceed to enable and use AI Assistant during your workflows. Refer to the following documentation for more information:

* [Enable AI Assistant access](./enable-ai-assistant-access.md)
* [Question guidance](./question-guidance.md)
* [Use AI Assistant](./use-ai-assistant.md)
