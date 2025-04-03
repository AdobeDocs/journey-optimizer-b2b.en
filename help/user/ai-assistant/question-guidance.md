---
title: Question guidance for AI Assistant
description: Placeholder
feature: AI Assistant
level: Beginner
---
# Question guidance for AI Assistant in Journey Optimizer B2B Edition

Review the following set of example questions for querying AI Assistant in Journey Optimizer B2B Edition. This information also includes tips for how to phrase your questions to get optimal responses from AI Assistant.

## Objective-based questions

The following example questions are grouped by objectives that you can accomplish when using AI Assistant:

| Objective | Description | Example |
| --- | --- | --- |
| Learning concepts and continuing workflows | As a novice user, you can use AI Assistant to learn Real-Time CDP and Adobe Journey Optimizer B2B Edition concepts and onboard yourself to products and features that you are unfamiliar with. <br>As an experienced user, you can use AI Assistant to solve an edge case that may be blocking your workflow. | <li>Tell me some use-cases for Real-Time CDP. <li>Explain the Buying Group concept to me. |
| Troubleshooting | Use AI Assistant to learn how to debug basic errors that you may encounter in your workflow. | <li>What does this error <ERROR_MESSAGE> mean? <li>Why am I not able to delete the audience named "..."? |
| Sandbox hygiene | Use AI Assistant to identify any duplicates or unused objects so you can efficiently maintain your sandbox. | <li>Can you show me account audiences that are similar? <li>Are there any schemas which do not have an associated dataset? |
| Value analysis | Use AI Assistant to identify your most used data objects and assess any performance indicators or find the most valuable data objects. | <li>How many accounts are in our "..." segment definition? <li>When were audiences activated to Experience Cloud Audiences destination? |
| Search | Use AI Assistant to find supported Experience Platform and Adobe Journey Optimizer B2B Edition objects, such as account audiences, datasets, destinations, schemas, sources, account journeys, buying group templates, and solution interests | <li>List the audiences containing "Luma" in the name that were used in account journeys. <li>What attributes are in the "Luma: Custom Actions" XDM schema? |
| Impact analysis | Use AI Assistant to identify data objects that have been used in certain workflows so that you can assess the impact of any changes. |<li>Which account audiences use `workEmail.address` in the "B2B Person" schema? <li>Which datasets are the ... `jobTitle` stored in? |

## Phrasing your questions

You must phrase your questions to AI Assistant with clarity and context in order to get as accurate a response as a possible. Refer to the following list of tips for guidance on how to ask a clear question with context:

* State your task and/or question in a concise manner.
* Avoid ambiguous language or overly complex syntax to facilitate comprehension.
* Provide relevant context regarding your task and/or question as context can help AI Assistant generate more relevant responses.

The following tables outline best practices you can follow when using AI Assistant:

| Do | Example |
| --- | --- |
| Be specific about the object or information that you want to retrieve or analyze.Try placing your data object names in quotes. If you only know a part of the object name, you may also specify that in the question. | Which datasets use the "B2B Account" schema?Show me the activated audiences which have "Account" in their names. Rank them by member count. |
| Avoid ambiguity and use clear languageUse precise terminology to ensure better clarity in your query.When asking questions regarding Adobe Experience Platform and Adobe Journey Optimizer B2B Edition, try to use terminology specific to Experience Platform or Adobe Journey Optimizer B2B Edition to improve relevance of responses. | How many members do I have in "My Account Audience"?How many Account Journeys uses Account Audience "My Account Audience"? |
| Provide context or specify a criteria to filter your results.Use a filter criteria in the questions to limit the volume of data in the response. | Show me account audiences that have not been activated and were created more than 6 months ago and have never been modified.Show me account journeys published in the last 7 days and uses an account audience that has more than 1000 members |

| Don't | Example |
| --- | --- |
| Use vague or ambiguous language. | Give me information about datasets.What does journey x do?How many users do I have in "ACME Audience"?Show segments.List attributes. |
| Make incomplete requests. | "Luma - Loyalty Dataset" |
| Assume knowledge without contexts. | Audiences in the last 6 months.Build a query for me.Create a journey for me |
| Formulate overly complex queries. | Provide a comprehensive analysis of data lineage across all objects and their dependencies. |
| Omit criteria or parameters. | Show me datasets. |

## Examples of unsupported questions

The following list includes examples of questions that are currently not supported by AI Assistant in Journey Optimizer B2B Edition.

* Which account audiences uses the workEmail.address field of ... field group in its condition? 
* Show me the number of active journeys using account audiences of size of over 10,000, 5000-10,000, 1000-5000, and below 1000, in a distribution visual
* Who made the last update on account journey x?
* How many active journeys add buying group members for solution interest x?
* What active journeys add buying group members for solution interest x?
* What is the most common decision maker title of buying group templates?
* Who are the decision makers for buying group template x?

## Next steps

For information about how to use the AI Assitant features during your workflows, read the AI Assistant UI guide.