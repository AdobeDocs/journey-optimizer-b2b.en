---
title: Audience Agent B2B
description: Audience Agent B2B in Journey Optimizer B2B Edition uses intent analysis and persona mapping to create buying groups and accelerate B2B marketing workflows.
feature: Agentic AI, Audiences
role: User
exl-id: c1210912-66ba-4b5f-8f3b-96eb6280c926
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
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
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
autotag-review: '2026-04-29T23:21:59.633Z'
---
# Audience Agent B2B

Powered by [Adobe Experience Platform Agent Orchestrator](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator), Audience Agent B2B is available in Journey Optimizer B2B Edition. Using this agent enhances efficiency and effectiveness in exploring and scaling audiences, accelerating buying group creation and seamless workflows for journey activation:

* **_Prioritize target audiences by intent_**: Infer personas based on product intent for various audiences and streamline campaign planning, reducing time spent on audience validation.

* **_Leverage AI to detect and create buying groups_**: Use AI, structured, unstructured data, and unified first-party data to streamline buying group discovery and creation.

![Audience Agent B2B in full page mode](./assets/audience-agent-full.png){width="700" zoomable="yes"}

>[!PREREQUISITES]
>
>To use Audience Agent B2B, there are required data definitions and mappings:<br/>
>
>* [Intent data taxonomy/mapping](../admin/intent-data.md)
>* [XDM field taxonomy/mapping](#xdm-data-prerequisites)

## Audience Agent B2B capabilities

| Area | What it does | Business value |
| ---- | ------------ | -------------- |
| Intent analysis | <li> Measure account intent strength (such as low, medium, and high) for specific products. <li>Compare product interest trends over time (such as top products in the last _n_ days). <li>Identify accounts actively showing interest in specific products. <li>Surface engagement patterns that combine account activity with persona coverage. | <li>Helps teams focus on the right accounts at the right time. <li>Improves pipeline quality by prioritizing accounts with genuine purchase signals. <li>Enables proactive engagement before competitors act. |
| Persona mapping | <li>Detect and rank the top personas by product intent. <li>Identify personas involved in buying one or multiple products. <li>Map personas to functional roles (such as _Champion_, _Decision Maker_, and _Influencer_) with justification. <li>Validate why a given person is considered a champion. | <li>Ensures that the sales team engages the true decision-makers and influencers. <li>Reduces wasted effort on low-impact contacts. <li>Increases win rates by aligning outreach with buyer power dynamics. |
| Buying group evaluation | <li>Assess buying group size (for example, groups with more than _n_ members). <li>Measure persona coverage across accounts (for example, below _x_%). <li>Track role distribution and coverage gaps within buying groups. <li>Highlight accounts with champions identified in recent deals. | <li>Reveals coverage gaps that could stall deals. <li>Strengthens multi-threading strategies by ensuring full role representation. <li>Improves deal health tracking through group-level engagement insights. |
| Buying group creation & actionability | <li>Recommend role-to-persona mappings based on observed persona and role patterns. <li>Generate a buying group role template for a specified product. <li>Support template customization by including or excluding specific personas and roles. <li>Validate that required roles are defined before buying groups are created. | <li>Reduces manual effort and risk of incomplete buying group templates. <li>Ensures role coverage is validated before creation, mitigating the risk of coverage gaps. <li>Turns analysis insights into immediate, operational next steps. |

## Limitations

Audience Agent B2B depends on configured intent taxonomy, XDM field mappings, and experience event data. Insights are less reliable when opportunity data is incomplete, the intent taxonomy is missing or out of date, or required profile and account identifiers are not mapped. For intent calculation, the agent processes only these experience events: `directMarketing.emailClicked`, `directMarketing.emailOpened`, `directMarketing.emailUnsubscribed`, and `web.webpagedetails.pageViews`.

## Prompt examples

These prompt samples demonstrate some of the ways that you can use the agent:

* Show the trend window: earliest and latest updated for account product intent per product.
* For `<product>`, list buying groups with product intent and scores.
* For `<product>`, list personas and roles with their opportunity metrics (win rate, membership rate, counts).
* For accounts in `<industry>`, what is the average account persona coverage for `<product>`?
* Which accounts have low intent for any product but still have open opportunities (worth nurturing)?
* Which accounts added new intent signals for `<account_name>` this week?
* Show me the personas associated with `<product>`.
* Show me the role to persona mapping recommendation for `<product>`.
* Create a buying group template for `<product>`.
* Create a buying group template for `<product>` without the `<persona>` persona and remove the `<role>` role.

## Concepts

| Concept | Explanation |
| ------- | ----------- |
| Audience detection | Behind the scenes, the agent looks at first-party intent signals based on two things: how engaged people are with your brand, and the kinds of personas that they represent. The analysis looks back over the past 18 months of activity to detect product intent across everyone in the account, especially during the time leading up to an opportunity close. This analysis helps the agent to highlight the personas most likely to influence the deal.<br/><br/>Sometimes accounts don't have all their opportunity data in perfect shape, which is fine and the agent can still detect product intent purely from engagement patterns. |
| Persona | Personas represent the types of people engaging within an account. The agent builds them by looking at job title, function, and seniority level, and then normalizing that information so it is consistent across different accounts. That way, instead of getting lost in messy titles, you can quickly see if you are reaching decision-makers, influencers, or support roles. Personas help you understand who is showing interest, not just how much interest there is. |
| Mapping buying group roles | After personas are mapped to roles, you bring them together into a buying group—the full team inside the account that is most likely to influence or decide on the purchase. Each role (such as _decision maker_, _influencer_, or _champion_) adds a piece of the picture so you have a clear view of the committee driving the deal.<br/><br/>The agent maps each identified persona to the role they are most likely to play for a specific product, based on job title, function, seniority, and other attributes you configure. It also shows coverage for each role so you can see which roles are well-represented and where gaps remain in your engagement strategy. |
| Using opportunity data to detect persona | To give you the most accurate view of who is engaging and where their interests lie, the agent approaches persona ranking and product intent according to the following: <ul><li>Best case scenario: If you can provide data like _Opportunity Stage_, _Opportunity Close Date_, and a clear _Opportunity-to-Product Mapping_, the agent can confidently rank personas per product.<li>This ranking provides a precise understanding of engagement and interest across the account. </ul>But the agent knows that the data is not always complete, which is OK. It includes smart fallbacks to keep things moving:<ul><li>The agent analyzes the volume of activities, giving more weight to recent ones using time decay.<li>This weighting allows the agent to differentiate and rank personas, even without full opportunity data. </ul>When it comes to linking opportunities to products, here's how the agent handles it:<ul><li>_Ideal_: You provide or help the agent create the mapping table.<li>_If not available_: the agent uses fuzzy matching to connect the dots.<li>_No linkage at all_: The agent infers product intent based on recent activities prior to the close date.</ul>This layered approach ensures that the agent can still deliver meaningful insights, even when the data isn't perfect. |
| Opportunity analysis | The agent looks at historical opportunity data to understand which factors most strongly predict a win, and it uses three core dimensions to do that:<ol><li>Win rate: Shows how often deals are successfully closed when certain personas are involved. If accounts with a specific persona pattern (like a technical evaluator or a VP-level decision maker) tend to convert more often, the model gives higher weight to that pattern. This information is a percentage of total opportunities, such as opportunities that are closed or won.<li>Membership rate: Measures how frequently a persona type shows up across opportunities for a given product. If certain personas consistently appear in successful deals, it indicates that they play a critical role in the buying process.<li>Persona influence: Quantifies how much a given persona contributes to the outcome, not just whether they are present, but how their engagement or activity level correlates with wins.</ol>Together, these signals help infer which personas have the strongest impact on purchase outcomes, even when opportunity data is incomplete. Over time, it allows the system to surface high-impact personas and patterns that are most predictive of deal success, which then inform account intent, persona mapping, and buying group recommendations. |
| Intent | When someone visits a web page or clicks an email link related to a product, it is a signal that they are interested, and that is called _intent_.<br/><br/>The agent starts with a taxonomy, which is basically a list of the customer's products and the keywords that describe them. This information helps the agent to understand what each piece of content or interaction is about.<br/><br/>Next, the agent uses that taxonomy to label visitor activity, such as which keywords or products their actions relate to.<br/><br/>Then, the agent looks at how deeply someone engages, such as how many pages they visit or how often they interact. It uses this information to calculate their individual intent score for specific keywords, products, or product categories. It buckets each intent score into _High_, _Medium_, or _Low_ intent to indicate the interest strength. (Low intent: `<=0.2`, Medium intent: `0.2 < score <= 0.6`, High intent: `0.6 < score <= 1`)<br/><br/>Finally, the agent combines the intent scores of all people from the same company (account) to see the overall account-level intent, showing which products or topics that company seems most interested in. |
| Roles influencing a buying group | Each buying group is comprised of roles who contribute differently to the purchase decision, such as _Decision Maker_, _Influencer_, _Champion_, and _End User_. Each role has a varying degree of impact.<br/><br/>Decision Makers hold the most influence and typically control budget approvals. Influencers shape evaluation and recommendations. Champions help build internal consensus, while End Users validate the product's fit.<br/><br/>By showing you these roles, the agent helps you understand who is driving the buying decision, where your engagement is strongest, and where coverage gaps might exist. This information enables you to focus on the roles that matter most for this product. |
| Persona or role coverage | For any given product, there is usually a set of key roles and personas that are known to influence the purchase (_N_ personas or roles).<br/><br/>For each account, the agent calculates coverage by checking how many of those _N_ roles are represented by at least one person within that account.<br/><br/>If all _N_ roles are present, the account has full coverage. If only some roles are represented, the coverage is partial.<br/><br/>In simple terms, role and persona coverage measure how complete your buying group is for a product, based on whether all the important decision-makers, influencers, and champions are included. |

## XDM data prerequisites

Audience Agent provides insights on accounts showing first-party intent for products and computes personas and roles based on the defined data. Ensure that the following prerequisite data is configured to use Audience Agent capabilities:

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
      <td>First name of person, used by Audience Agent to display names in the UI when met with any criteria</td>
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
      <td>Full Name of person, used by Audience Agent to display names in UI when met with any criteria</td>
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
      <td>Last Name of person, used by Audience Agent to display names in UI when met with any criteria</td>
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
      <td>Name of Account used by Audience Agent to display in the UI when met with any criteria posed in the user query</td>
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
      <td>Description of Account/Company used by Audience Agent to apply filter on accounts based on user query in UI </td>
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
      <td>Industry of Account/Company used by Audience Agent to apply filter on accounts based on user query in UI </td>
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
      <td>Billing Address of Account/Company used by Audience Agent to apply filter on accounts based on user query in UI </td>
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
      <td>Name of Opportunity used by Audience Agent </td>
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
      <td>Description of Opportunity used by Audience Agent </td>
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

Audience Agent leverages first-party intent detected within Journey Optimizer B2B Edition:

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
      <td>Get the type of event since the agent processes only four events (<span>directMarketing.emailClicked, directMarketing.emailOpened, directMarketing.emailUnsubscribed, web.webpagedetails.pageViews)</span>
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
      <td>Used to fetch the email content from the Marketo Engage data center; it is comprised of (SourceID@SourceInstanceID.SourceType)</td>
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
