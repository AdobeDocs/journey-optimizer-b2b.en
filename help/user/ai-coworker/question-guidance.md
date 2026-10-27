---
title: Question guidance for [!DNL Coworker] chat
description: Write effective [!DNL Coworker] chat questions with best practices, examples, and phrasing tips to get optimal responses in Journey Optimizer B2B Edition.
feature: AI Assistant
role: User
level: Beginner
exl-id: 65541246-7f4f-442f-8293-df036ea1c4ac
autotag-review: '2026-06-05T16:08:18.792Z'
TQID: 'https://experienceleague.adobe.com/14sGSyP1nI123o2II9rkVQh-ECcEr6BcyfnMnVlrjlU'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Question guidance for [!DNL Coworker] chat

Review the following example questions for querying [!DNL Coworker] to enable [!DNL Adobe Journey Optimizer B2B Edition] workflows. This information also includes tips for how to phrase your questions to get optimal responses from [!DNL Coworker] chat.

## Objective-based questions

The following example questions are grouped according to objectives that you can accomplish when using [!DNL Coworker] chat:

| Objective | Description | Example |
| --- | --- | --- |
| Learning concepts and continuing workflows | As a novice user, you can use [!DNL Coworker] chat to learn [!DNL Adobe Real-Time Customer Data Platform] and [!DNL Journey Optimizer B2B Edition] concepts, and onboard yourself to products and features that you are unfamiliar with. <br>As an experienced user, you can use [!DNL Coworker] chat to solve an edge case that may be blocking your workflow. | <li>Tell me some use-cases for [!DNL Real-Time Customer Data Platform]. <li>Explain the Buying Group concept to me. |
| Troubleshooting | Use [!DNL Coworker] chat to learn how to debug basic errors that you may encounter in your workflow. | <li>What does this error <ERROR_MESSAGE> mean? <li>Why am I not able to delete the audience named "..."? |
| Sandbox hygiene | Use [!DNL Coworker] chat to identify any duplicates or unused objects so you can efficiently maintain your sandbox. | <li>Can you show me account audiences that are similar? <li>Are there any schemas which do not have an associated dataset? |
| Value analysis | Use [!DNL Coworker] chat to identify your most used data objects and assess any performance indicators or find the most valuable data objects. | <li>How many accounts are in our "..." segment definition? <li>When were audiences activated to Experience Cloud Audiences destination? |
| Search | Use [!DNL Coworker] chat to find supported [!DNL Adobe Experience Platform] and [!DNL Journey Optimizer B2B Edition] objects, such as account audiences, datasets, destinations, schemas, sources, account journeys, buying group templates, and solution interests | <li>List the audiences containing "Luma" in the name that were used in account journeys. <li>What attributes are in the "Luma: Custom Actions" XDM schema? |
| Impact analysis | Use [!DNL Coworker] chat to identify data objects that have been used in certain workflows so that you can assess the impact of any changes. |<li>Which account audiences use `workEmail.address` in the "B2B Person" schema? <li>Which datasets are the ... `jobTitle` stored in? |

## Phrasing your questions

To get as accurate a response as possible, phrase your questions to [!DNL Coworker] chat with clarity and context. Refer to the following list of tips for guidance on how to ask a clear question with context:

* State your task and/or question in a concise manner.
* Avoid ambiguous language or overly complex syntax to facilitate comprehension.
* Provide relevant context regarding your task and/or question as context can help [!DNL Coworker] chat generate more relevant responses.

The following tables provide some recommendations that you can follow when using [!DNL Coworker] chat:

| Do | Example |
| --- | --- |
| <li>Be specific about the object or information that you want to retrieve or analyze. <li>Try placing your data object names in quotes. <li>If you only know a part of the object name, you may also specify that in the question. | <li>Which datasets use the "B2B Account" schema? <li>Show me the activated audiences which have "Account" in their names. Rank them by member count. |
| <li>Avoid ambiguity and use clear language. <li>Use precise terminology to ensure better clarity in your query. <li>When asking questions regarding [!DNL Experience Platform] and [!DNL Journey Optimizer B2B Edition], try to use terminology specific to [!DNL Experience Platform] or [!DNL Journey Optimizer B2B Edition] to improve the relevance of responses. | <li>How many members do I have in "My Account Audience"? <li>How many account journeys use Account Audience "My Account Audience"? |
| <li>Provide context or specify a criteria to filter your results. <li>Use a filter criteria in the questions to limit the volume of data in the response. | <li>Show me account audiences that have not been activated and were created more than 6 months ago and have never been modified. <li>Show me account journeys published in the last 7 days and uses an account audience that has more than 1000 members |

| Don't | Example |
| --- | --- |
| Use vague or ambiguous language. | <li>Give me information about datasets. <li>What does journey x do? <li>How many users do I have in "ACME Audience"? <li>Show segments. <li>List attributes. |
| Make incomplete requests. | <li>"Luma - Loyalty Dataset" |
| Assume knowledge without contexts. | <li>Audiences in the last 6 months. <li>Build a query for me. <li>Create a journey for me |
| Formulate overly complex queries. | <li>Provide a comprehensive analysis of data lineage across all objects and their dependencies. |
| Omit criteria or parameters. | <li>Show me datasets. |

## Examples of unsupported questions

The following list includes examples of questions that [!DNL Coworker] chat does not currently support in [!DNL Journey Optimizer B2B Edition]:

* Which account audiences use the workEmail.address field of ... field group in their condition? 
* Show me the number of active journeys using account audiences of size over 10,000, 5000-10,000, 1000-5000, and below 1000, in a distribution visual
* Who made the last update on account journey x?
* How many active journeys add buying group members for solution interest x?
* What active journeys add buying group members for solution interest x?
* What is the most common decision-maker title of buying group templates?
* Who are the decision makers for buying group template x?

## Next steps

For instructions on using chat features in the [!DNL CX Coworker] app, see the [CX Coworker interface guide](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}.
