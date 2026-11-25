---
title: Audience Skills for B2B Accounts and People
description: Learn about audience skills for B2B accounts and people. Explore product intent, identify personas, evaluate role coverage, and create buying group templates.
feature: Agentic AI, Audiences
role: User
exl-id: c1210912-66ba-4b5f-8f3b-96eb6280c926
autotag-review: '2026-06-05T16:43:42.459Z'
TQID: 'https://experienceleague.adobe.com/d7KMYbH0NpoYGnBdTCmCpzLgpGIYfNP-YIFCQUjZpIg'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: afadf741-c5fe-42cd-8013-23bb6ff2d1bc
    internal-label: Buying Groups
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
subfeature_v2:
  - id: ff10f619-348f-47e3-99bf-3ce4c817cf2c
    internal-label: Agentic AI
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
---
# Audience skills for B2B accounts and people

Use audience skills for B2B in the [!DNL CX Coworker] interface. Explore product intent across accounts and people. Identify relevant personas, evaluate buying group coverage, and create buying group role templates.

* Assess account interest in specific products and compare intent trends.
* Identify people and personas associated with product interest.
* Review buying group roles and identify coverage gaps.
* Generate and refine buying group role templates.

>[!PREREQUISITES]
>
>Before using audience skills for B2B accounts and people, configure the following data definitions and mappings:
>
>* [Intent data taxonomy and mapping](../admin/intent-data.md)
>* [XDM field mapping](#xdm-data-prerequisites)

Click the _Ask [!DNL Coworker]_ ( ![Ask [!DNL Coworker]](../assets/do-not-localize/icon-ask-coworker.svg) ) icon at the top of the application to open the [!DNL Coworker] application. Enter your natural language prompt in the chat interface.

![Audience prompt in [!DNL CX Coworker]](./assets/audience-skills-prompt.png){width="800" zoomable="yes"}

## Audience skill focus areas

Use audience skill focus areas to explore account intent, understand people and personas, and prepare buying group templates.

| Focus | Tasks |
| ----- | ----- |
| Account intent | Assess account intent for specific products using low, medium, and high intent levels. Compare product interest trends over time and identify accounts showing interest in specific products. Review engagement patterns alongside persona coverage. |
| People and personas | Identify and rank personas by product intent across one or more products. Review opportunity metrics, including win rate, membership rate, and counts. Map personas to roles such as _Champion_, _Decision Maker_, and _Influencer_, and review explanations for role assignments. |
| Buying group coverage | Evaluate buying group size and persona coverage across accounts. Review role distribution and identify missing personas or roles. Find accounts with champions identified in recent deals. |
| Buying group templates | Generate buying group role templates for specific products and review recommended persona mappings. Refine templates by including or excluding personas and roles. Validate required roles before creating buying groups. |

## Limitations

Audience insights depend on configured intent taxonomy, XDM field mappings, and experience event data. Incomplete opportunity data, missing or outdated taxonomy, or missing profile and account identifiers can reduce insight reliability.

Intent calculation uses only these experience events: `directMarketing.emailClicked`, `directMarketing.emailOpened`, `directMarketing.emailUnsubscribed`, and `web.webpagedetails.pageViews`.

## Prompt examples

Enter the following prompts in the [!DNL CX Coworker] interface to explore account intent, understand people and personas, and prepare buying group templates.

### Account intent

Explore account interest in products and review changes in intent.

* Show the trend window: earliest and latest updates for account product intent per product.
* Which accounts have low intent for any product but still have open opportunities (worth nurturing)?
* What new intent signals were recorded for `<account_name>` this week?

### People and personas

Identify personas associated with product interest and review recommended buying group roles.

* Show me the personas associated with `<product>`.
* Show me the role to persona mapping recommendation for `<product>`.
* For `<product>`, list personas and roles with their opportunity metrics (win rate, membership rate, counts).

### Buying groups and templates

Review buying group intent and coverage, then generate or refine templates.

* For `<product>`, list buying groups with product intent and scores.
* For accounts in `<industry>`, what is the average account persona coverage for `<product>`?
* Create a buying group template for `<product>`.
* Create a buying group template for `<product>` without the `<persona>` persona and remove the `<role>` role.

## Concepts

Use these concepts to interpret account intent, persona rankings, and buying group recommendations.

| Concept | Explanation |
| ------- | ----------- |
| Audience detection | Analyze first-party engagement signals across people in an account to identify product interest and relevant personas. The analysis considers the previous 18 months of activity, including activity before opportunity close. Engagement patterns can indicate product intent when opportunity data is incomplete, but missing data can reduce insight reliability. |
| Persona | Personas group people by normalized job title, function, and seniority. Use personas to understand who is engaging within an account, including decision-makers, influencers, and support roles. |
| Mapping buying group roles | Map personas to product-specific buying group roles based on job title, function, seniority, and configured attributes. These roles represent the people within an account who influence or decide on a purchase. Review coverage to identify missing roles. |
| Opportunity data for persona ranking | Opportunity stage, close date, and opportunity-to-product mappings support persona ranking for each product. When opportunity data is incomplete, ranking uses activity volume and time decay to give recent activity more weight.<br/><br/>Product linkage uses a supplied or generated opportunity-to-product mapping table when available. Otherwise, fuzzy matching links opportunities to products. If no linkage is available, product intent is inferred from recent activity before the opportunity close date. These fallback methods do not eliminate the reliability limitations of incomplete data. |
| Opportunity analysis | Historical opportunity analysis uses three dimensions to identify persona patterns associated with purchase outcomes:<ul><li>Win rate: Measures how often opportunities are won when particular personas are involved. Persona patterns associated with higher win rates receive more weight.</li><li>Membership rate: Measures how frequently a persona appears in opportunities for a given product.</li><li>Persona influence: Measures how persona engagement or activity correlates with wins, beyond whether the persona is present.</li></ul>These signals inform account intent, persona mapping, and buying group recommendations. |
| Intent | Intent indicates product interest through engagement, such as webpage visits or email link clicks. Product taxonomy connects engagement activity to keywords, products, and product categories. Engagement depth and frequency determine individual intent scores for each keyword, product, or product category.<br/><br/>Scores indicate interest strength: Low intent: `<=0.2`, Medium intent: `0.2 < score <= 0.6`, High intent: `0.6 < score <= 1`.<br/><br/>Individual intent scores are aggregated across people in the same account to determine account intent. |
| Roles influencing a buying group | Buying group roles represent different contributions to a purchase decision. _Decision Makers_ typically control budget approvals. _Influencers_ shape evaluation and recommendations. _Champions_ build internal consensus. _End Users_ validate product fit.<br/><br/>Review role assignments and coverage to understand who influences the decision and where engagement gaps remain. |
| Persona or role coverage | Coverage measures how many expected personas or roles have at least one representative within an account. For a product with _N_ expected personas or roles, full coverage means all _N_ are represented. Partial coverage means some are missing. Use coverage to assess buying group completeness and identify gaps. |

## XDM data prerequisites

Configure the following XDM field mappings to support account intent analysis, persona identification, and buying group role mapping.

### XDM field mapping

<table>
  <tbody>
    <tr>
      <th>XDM Field</th>
      <th>Entity</th>
      <th>Business Definition</th>
      <th>Additional detail</th>
    </tr>
    <tr>
      <td>
        <p>
          <span>b2b.accountKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>Profiles</span>
        </p>
      </td>
      <td>Account Identifier, used in joins to opportunity, event and intent data</td>
      <td rowspan="2">Opportunity analysis<br/>Account Exploration<br/>
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>b2b.personKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>Profiles</span>
        </p>
      </td>
      <td>Person Identifier, used in joins involving event data to profile data</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>extendedWorkDetails.departments</span>
        </p>
      </td>
      <td>
        <p>
          <span>  Profiles</span>
        </p>
      </td>
      <td>Job Department of the profile/person</td>
      <td rowspan="5">
        <p>
          <br/>
        </p>
        <p>Persona Mapping</p>
      </td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>extendedWorkDetails.jobTitle</span>
        </p>
      </td>
      <td>
        <p>
          <span>  Profiles</span>
        </p>
      </td>
      <td>Job Title of profile/person used in persona calculation</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>person.name.firstName</span>
        </p>
      </td>
      <td>
        <p>
          <span >Profiles</span>
        </p>
      </td>
      <td>Displays the person's first name in results that match your query.</td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>person.name.fullName</span>
        </p>
      </td>
      <td>
        <p>
          <span> Profiles</span>
        </p>
      </td>
      <td>Displays the person's full name in results that match your query.</td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>person.name.lastName</span>
        </p>
      </td>
      <td>
        <p>
          <span> Profiles</span>
        </p>
      </td>
      <td>Displays the person's last name in results that match your query.</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span> Accounts</span>
        </p>
      </td>
      <td>Account Identifier, used in joins to opportunity, event and intent data</td>
      <td>Opportunity analysis<br/>Account Exploration</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountName</span>
        </p>
      </td>
      <td>
        <p>
          <span>Accounts</span>
        </p>
      </td>
      <td>Displays the account name in results that match your query.</td>
      <td rowspan="4">
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>Account Exploration</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountDescription</span>
        </p>
      </td>
      <td>
        <p>
          <span>Accounts</span>
        </p>
      </td>
      <td>Supports account filtering by account description based on your query.</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountOrganization.industry</span>
        </p>
      </td>
      <td>
        <p>
          <span>  Accounts</span>
        </p>
      </td>
      <td>Supports account filtering by industry based on your query.</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountBillingAddress.region</span>
        </p>
      </td>
      <td>
        <p>
          <span>  Accounts</span>
        </p>
      </td>
      <td>Supports account filtering by billing address region based on your query.</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>Opportunity</span>
        </p>
      </td>
      <td>Account Identifier, used in joins to opportunity, event and intent data</td>
      <td rowspan="2">
        <p>Opportunity Analysis<br/>Account Exploration</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>Opportunity</span>
        </p>
      </td>
      <td>Opportunity Identifier, used in joins to account data</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityName</span>
        </p>
      </td>
      <td>
        <p>
          <span> Opportunity</span>
        </p>
      </td>
      <td>Opportunity name used in opportunity analysis.</td>
      <td rowspan="5">
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>Opportunity Analysis</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>isWon</span>
        </p>
      </td>
      <td>
        <p>
          <span>Opportunity</span>
        </p>
      </td>
      <td>Whether the opportunity is won (binary)</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityDescription</span>
        </p>
      </td>
      <td>
        <p>
          <span>Opportunity</span>
        </p>
      </td>
      <td>Opportunity description used in opportunity analysis.</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityAmount</span>
        </p>
      </td>
      <td>
        <p>
          <span>Opportunity</span>
        </p>
      </td>
      <td>Amount of $ involved in Opportunity</td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>opportunityType</span>
        </p>
      </td>
      <td>
        <p>
          <span>Opportunity</span>
        </p>
      </td>
      <td>Type of Opportunity</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityStage</span>
        </p>
      </td>
      <td>
        <p>
          <span> Opportunity</span>
        </p>
      </td>
      <td>Stage of Opportunity (closed won or closed lost or any of intermediate stages) </td>
      <td rowspan="4">
        <p>Opportunity analysis<br/>Account Exploration</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>actualCloseDate</span>
        </p>
      </td>
      <td>
        <p>
          <span>Opportunity</span>
        </p>
      </td>
      <td>Actual closed date of opportunity</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>expectedCloseDate</span>
        </p>
      </td>
      <td>
        <p>
          <span> Opportunity</span>
        </p>
      </td>
      <td>Expected Close Date of Opportunity</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>extSourceSystemAudit.createdDate</span>
        </p>
      </td>
      <td>
        <p>
          <span>Opportunity</span>
        </p>
      </td>
      <td>Created date for this opportunity</td>
    </tr>
  </tbody>
</table>

### Taxonomy data

Audience skills use first-party intent data from [!DNL Adobe Journey Optimizer B2B Edition]. Intent calculation connects product taxonomy with engagement activity and aggregates individual scores at the account level.

1. Intent computation requires taxonomy data (customer products and corresponding keywords) from Customers > Taxonomy
1. Taxonomy data is used to label event data (asset labeling). This data provides insights for what keywords and products visitors are interested in based on their event data > Asset Labeling 
1. Labeled assets (event data) are combined with visitor behaviors (number of pages visited) to determine a visitor intent at keyword, product and product category level → Intent calculation
1. Intent scores at a visitor profile level are aggregated at account level to determine account intent in a given keyword, product and product category > Intent Account Aggregation

The following fields are required in addition to [configuring the intent taxonomy](../admin/intent-data.md):

<table>
  <tbody>
    <tr>
      <th>XDM Field</th>
      <th>Entity</th>
      <th>Business Definition</th>
    </tr>
    <tr>
      <th>
        <br/>
      </th>
      <th>
        <br/>
      </th>
      <td>person profile</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>_acp_system_metadata.primaryIdentity.namespace.code<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Profile</span>
        </p>
      </td>
      <td>Helps identify a person (email or b2b_person) identifier</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>_acp_system_metadata.primaryIdentity.id
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Profile</span>
        </p>
      </td>
      <td>namespace_id</td>
    </tr>
    <tr>
      <td>
        <ul>
          <li>keyword_id</li>
          <li>keyword_name</li>
          <li>product_id</li>
          <li>product_name</li>
          <li>product_category_id</li>
          <li>product_category_name</li>
        </ul>
      </td>
      <td>
        <p>
          <br/>
        </p>
      </td>
      <td>Used as a taxonomy to label assets (experience events, such as clicked emails, visited webpages)</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>timestamp</span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Used for time to get backfill and incremental run</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>eventType</span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Identifies the event type. Intent calculation uses only <code>directMarketing.emailClicked</code>, <code>directMarketing.emailOpened</code>, <code>directMarketing.emailUnsubscribed</code>, and <code>web.webpagedetails.pageViews</code>.
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingName</span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Only for reference/bookkeeping; Information about the campaign name</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingKey.sourceID</span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Only for reference/bookkeeping; Information about the source ID for whom the email is targeted</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingKey.sourceInstanceID<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Only for reference/bookkeeping; Information of the source instance for whom the email is targeted</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingKey.sourceKey<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Used to fetch the email content from the [!DNL Adobe Marketo Engage] data center. It comprises (SourceID@SourceInstanceID.SourceType).</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingKey.sourceType<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Only for reference/bookkeeping; Information about the type of the source or where the source originated from </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Information about the webpage visit source origin</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.name<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Actual url used to get content</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.queryParameters</span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Additional query parameter for the URL used to fetch targeted content </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.isPersonalizedURL</span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>only for reference/bookkeeping</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.sourceID<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Only for reference/bookkeeping; Information about the source ID for whom the email is targeted</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.sourceInstanceID<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>Experience Event</span>
        </p>
      </td>
      <td>Only for reference/bookkeeping; Information about the source instance for whom the email was targeted</td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.sourceKey<br/>
          </span>
        </p>
      </td>
      <td>
        <span>Experience Event</span>
      </td>
      <td>Only for reference/bookkeeping; it is comprised of (SourceID@SourceInstanceID.SourceType)</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.sourceType</span>
        </p>
      </td>
      <td>
        <span>Experience Event</span>
      </td>
      <td>Only for reference/bookkeeping; Information for the type of the source or where the source originated from</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.URL</span>
        </p>
      </td>
      <td>
        <span>Experience Event</span>
      </td>
      <td>Used to fetch actual url if web.webPageDetails.name does not have it.</td>
    </tr>
  </tbody>
</table>
