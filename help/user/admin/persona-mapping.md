---
title: Persona Mapping
description: Learn how to configure personas for account-based marketing by mapping person attributes to create streamlined role templates for buying groups.
feature: Setup, Buying Groups
hide: yes
hidefromtoc: yes
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
role: Admin
---
# Persona mapping

Personas are a key aspect in an account-based marketing (ABM) approach because they help marketers adjust their strategies to the specific needs, preferences, and pain points of individuals within target accounts. Marketers can create detailed profiles for each persona, including their background, responsibilities, pain points, and preferred communication channels. With these definitions, administrators can configure personas according to person attributes in Journey Optimizer B2B Edition so that roles templates can use streamlined and consistent role conditions that capture these personas.

<!-- Currently there is no insight into what persona goes into what role. With buying group agent, when asked questions about, what should be the size of the buying group, what persona should be in that buying group, what role do they play, etc, then agent will analyze all the data, (opportunity data, engagement data, sales conversation, etc) and informs the user that the buying group needs 7 persona, e.g.CMO, VP of marketing, marketing leader, Marketing ops, etc. 

Then based on what agent informed, users can create a template with those personas. -->
Persona definition and usage limitations:

* You can have up to 20 personas defined in the _[!UICONTROL Persona mapping]_ list.
* Each persona can include up to five attributes in its definition.
* Across all defined personas, you can use up to ten different person attributes.

>[!BEGINSHADEBOX]

**Use case: job title variations**

Many marketing and sales teams use job titles as a way to identify different personas within an account. But titles for contacts can be inconsistent and use numerous variations for similar roles. When building buying group roles templates, it can require that you define every possible related job title for a given role. You can simplify these definitions and bring people with similar job titles under one inferred persona, which you can then leverage across different roles templates for buying groups.

For example, you might configure a persona called _Product Management_ and define it using the job title attribute for values of _Product Manager_, _Sr. Product Manager_, _Senior Product Manager_, _PM_, _Sr. PM_, _Principal PM_, and _Principal Product Manager_. Then, use this persona in a Roles template where the condition matches on _Persona is Product Management_. Using the configured persona, creating each roles template is streamlined and does not require a complicated condition that can match against every possible job title.

>[!ENDSHADEBOX]

## Access the configured personas

1. In the left navigation, choose **[!UICONTROL Administration]** > **[!UICONTROL Configurations]**.

1. Click **[!UICONTROL Persona mapping]** on the intermediate panel to display the list of personas.

   ![Access the configured personas](./assets/configuration-engagement-scoring-list.png){width="800" zoomable="yes"}

   From this page, you can [create](#create-an-engagement-score-model), [edit](#change-the-engagement-weighting-settings), or [delete](#delete-a-persona) personas.

   The Persona mapping list. is organized as a table and displays the most recently updated personas at the top (sorted by _[!UICONTROL Last update]_). You can customize the displayed table by clicking the _Column settings_ ( ![Column settings](../assets/do-not-localize/icon-column-settings.svg) ) icon in the top-right corner and selecting or clearing the column checkboxes.

  ![Columns to display in the persona mapping list](./assets/configuration-engagement-scoring-list-columns.png){width="300"}

1. To access the details for a persona, click the name.
   
### Default personas

The _Persona mapping_ list includes five default personas that are defined according to the job tittle attribute. You can edit any of these default personas according to the needs of your organization:

| Persona | Job titles |
| ------- | ---------- |
| CXO / EVP – CXO / Executive Vice President | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| SVP / VP – Senior Vice President / Vice President | SVP of Marketing, VP of Sales, SVP of Operations, VP of Product, VP of IT |
| Senior Director / Director – Senior Director / Director | Director of Engineering, Senior Director of Product, Director of Finance, Director of Customer Success |
| Senior Manager / Manager – Senior Manager / Manager | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| Individual Contributor – Individual Contributor | Account Executive, Software Engineer, Marketing Specialist, Customer Success Representative |
| Analyst – Analyst | Business Analyst, Data Analyst, Market Research Analyst, Financial Analyst, Operations Analyst |
| Developer – Developer | Front-End Developer, Back-End Developer, Full-Stack Developer, Mobile App Developer, DevOps Engineer |
| Professional Staff – Professional Staff | HR Specialist, Legal Counsel, Compliance Officer, Project Manager, Procurement Specialist |
| Consultant – Consultant | Management Consultant, IT Consultant, Business Process Consultant, Marketing Consultant |
| Other – Other | Industry Specialist, Independent Advisor, Freelance Consultant, Subject Matter Expert |

### List filtering

To locate the persona that you want, use the search and filter tools:

* Enter a text string into the search bar to match personas by name, 
   
   ![Filter the displayed event definitions](./assets/configuration-events-defs-list-filtered.png){width="700" zoomable="yes"}

* Click the _Filter_ ( ![Filter icon](../assets/do-not-localize/icon-filter.svg) ) icon at the top left to filter the displayed list  using any of these attributes:

   * ?
   * ?

## Create a persona

1. In the left navigation, choose **[!UICONTROL Administration]** > **[!UICONTROL Configuration]**.

1. Click **[!UICONTROL Persona mapping]** in the intermediate panel.

1. Click **[!UICONTROL Create persona]**.

1. Enter a unique **[!UICONTROL Name]** and **[!UICONTROL Description]** (optional) for the persona.

1. Select the attributes to use for matching the persona. 

   * Click **[!UICONTROL Select person attributes]**.

   * In the _[!UICONTROL Select person attributes]_ dialog, select the checkbox for each attribute that you want to map (a maximum of five).

      You can customize the displayed table by clicking the _Column settings_ ( ![Column settings](../assets/do-not-localize/icon-column-settings.svg) ) icon in the top-right corner.   

      To filter the attribute list by name, enter a text string into the search bar. You can also click the _Filter_ ( ![Filter icon](../assets/do-not-localize/icon-filter.svg) ) icon at the top left to filter the displayed list by type, _Standard_ or _Custom_.

   * Click **[!UICONTROL Save]**.

     The selected attributes are populated in the _[!UICONTROL Persona attributes]_ section.

1. For each attribute, enter the comma-separated values that you want to match for the attribute.

   In place of a value, you can also add a prompt that can be used to identify a match. For example, you could enter 

1. Click **[!UICONTROL Create]**.

## Edit a persona

1. To access the details for the persona, click the name.


## Delete a persona

Deleting a persona removes it from the _Persona mapping_ list and it is no longer available for use in roles templates.

1. On the _[!UICONTROL Persona mapping]_ page, locate the persona that you want to delete.

1. Next to the name, click the ellipses (**...**) icon for and choose **[!UICONTROL Delete]**.

1. In the confirmation dialog, click **[!UICONTROL Delete]**.
