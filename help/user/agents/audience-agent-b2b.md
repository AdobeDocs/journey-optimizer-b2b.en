---
title: Audience Agent for B2B
description: Audience Agent B2B in Journey OptimizerB2B Edition uses intent analysis and persona mapping to create buying groups and accelerate B2B marketing workflows. 
feature: Audiences, AI Assistant
role: User
---
# Audience Agent for B2B

Powered by [Adobe Experience Platform Agent Orchestrator](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator), Audience Agent B2B is available in Journey Optimizer B2B Edition. Using this agent enhances efficiency and effectiveness in exploring and scaling audiences, accelerating buying group creation and seamless workflows for journey activation:

* **_Prioritize target audiences by intent_**: Infer personas based on product intent for various audiences and streamline campaign planning, reducing time spent on audience validation.

* **_Leverage AI to detect buying groups_**: Use AI, structured, unstructured data, and unified first-party data to streamline buying group discovery and creation.

![Audience Agent for B2B in full page mode](./assets/audience-agent-full.png){width="700" zoomable="yes"}

>[!PREREQUISITES]
>
>To use Audience Agent for B2B, there are required data definitions and mappings:<br/>
>
>* [Intent data taxonomy/mapping](../admin/intent-data.md)
>* [XDM field taxonomy/mapping](#xdm-data-prerequisites)

## Audience Agent for B2B capabilities

| Area | What it does | Business value |
| ---- | ------------ | -------------- |
| Intent analysis | <li> Measure account intent strength (such as low, medium, and high) for specific products. <li>Compare product interest trends over time (such as top products in the last _n_ days). <li>Identify accounts actively showing interest in specific products. <li>Surface engagement patterns that combine account activity with persona coverage. | <li>Helps teams focus on the right accounts at the right time. <li>Improves pipeline quality by prioritizing accounts with genuine purchase signals. <li>Enables proactive engagement before competitors act. |
| Persona mapping | <li>Detect and rank the top personas by product intent. <li>Identify personas involved in buying one or multiple products. <li>Map personas to functional roles (such as _Champion_, _Decision Maker_, and _Influencer_) with justification. <li>Validate why a given person is considered a champion. | <li>Ensures that the sales team engages the true decision-makers and influencers. <li>Reduces wasted effort on low-impact contacts. <li>Increases win rates by aligning outreach with buyer power dynamics. |
| Buying group evaluation | <li>Assess buying group size (for example, groups with more than _n_ members). <li>Measure persona coverage across accounts (for example, below _x_%). <li>Track role distribution and coverage gaps within buying groups. <li>Highlight accounts with champions identified in recent deals. | <li>Reveals coverage gaps that could stall deals. <li>Strengthens multi-threading strategies by ensuring full role representation. <li>Improves deal health tracking through group-level engagement insights. |

## Prompt examples

These prompt samples demonstrate some of ways that you can use the agent:

* Show the trend window: earliest and latest updated for account product intent per product.
* For `<product>`, list buying groups with product intent and scores.
* For `<product>`, list personas and roles with their opportunity metrics (win rate, membership rate, counts).
* For accounts in `<industry>`, what is the average account persona coverage for `<product>`?
* Which accounts have low intent for any product but still have open opportunities (worth nurturing)?
* Which accounts added new intent signals for `<account_name>` this week?

## Concepts

| Concept | Explanation |
| ------- | ----------- |
| Audience detection | Behind the scenes, the agent looks at first-party intent signals based on two things: how engaged people are with your brand, and the kinds of personas that they represent. The analysis looks back over the past 18 months of activity to detect product intent across everyone in the account, especially during the time leading up to an opportunity close. This analysis helps the agent to highlight the personas most likely to influence the deal.<br/><br/>Sometimes accounts don't have all their opportunity data in perfect shape, which is fine and the agent can still detect product intent purely from engagement patterns. |
| Persona | Personas represent the types of people engaging within an account. The agent builds it by looking at job title, function, and seniority level, and then normalizing that information so it is consistent across different accounts. That way, instead of getting lost in messy titles, you can quickly see if you are reaching decision-makers, influencers, or support roles. Personas help you to understand who is showing interest, not just how much interest there is. <br/><br/> When the agent maps personas to buying group roles, it takes the type of identified persona, based on their job title, function, seniority, and any other attribute you choose to add, and align them to the roles that they are most likely to play in a purchase decision, such as _decision maker_, _influencer_, or _champion_. These roles are relevant to the specific product in question, so that you can see who matters most for that opportunity. The agent also shows coverage for each role, helping you quickly understand which roles are well-represented and where there may be gaps to fill in your engagement strategy. |
| Mapping buying group roles | After personas are mapped to roles, you bring them together into a buying group. Think of it as the full team inside the account that is most likely to influence or decide on the purchase. Each role (such as _decision maker_, _influencer_, or _champion_) adds a piece of the picture, so that you have a clear view of the whole committee driving the deal. <br/><br/> When you map personas to buying group roles, you take the type of identified persona, based on their job title, function, seniority, and any other attribute you choose to add, and align them to the role that they are most likely to play in a purchase decision, such as _decision maker_, _influencer_, or _champion_. These roles are relevant to the specific product in question, so that you can see who matters most for that opportunity. The agent shows coverage for each role, helping you quickly understand which roles are well-represented and where there may be gaps to fill in your engagement strategy. |
| Buying groups | Buying groups enable marketers to manage the true complexity of purchasing committees, not isolated leads or accounts. Adobe Journey Optimizer B2B Edition offers the tools (AI-driven insights, role-based journeys, and completeness tracking) to bring structure, personalization, and analytical clarity to that process, ultimately aligning marketing & sales more tightly around revenue outcomes.<br/><br/>Creating a buying group is really about bringing three key things together: the right audience, the product context, and the buying group roles. Here's a step-by-step preview of how it works: <ol><li>**Identify your audience** <ul><li>First, the agent uncovers the accounts that are most relevant to your product. This discovery includes accounts that already show interest and accounts with potential.<li>Within these accounts, it identifies the people (your key personas) who might influence or be part of the buying decision.<li>It chooses from the accounts to surface: an account list, or an account audience.</ul><li>**Consider the product context**<ul><li>Next, it looks at the product or solution that you are focusing on, which ensures that the identified personas are actually relevant to what you want to sell or promote.<li>It also helps highlight any gaps in coverage (maybe certain roles are missing for the product) so you know where to focus.</ul> <li>**Map personas to buying group roles** <ul><li>Finally, the agent maps those personas to specific buying group roles, like decision makers, influencers, and champions.<li>Based on this mapping, the agent can recommend a buying group composition for you, which you can review, adjust, or confirm.</ul> </ol> When these three components come together, it creates your buying group, complete with member details, roles, and insights ready to use.|
| Buying groups in a journey | Within a journey, a buying group can be used as the central unit of orchestration, which allows marketers to design experiences that adapt to the dynamics of the group rather than treating members in isolation. For example, you can target the entire group with coordinated messaging, while also tailoring role-specific content to decision makers, influencers, or end users. As intent signals and engagement data flow in, journeys can branch based on group readiness, surface alerts for sales when critical roles engage, or automatically trigger nurture steps if key personas are missing. This flow ensures that every touchpoint (from emails to account-based ads to sales outreach) works together to move the group forward in their buying process, accelerating consensus and reducing friction on the path to purchase. |
| Journeys in Journey Optimizer B2B Edition | A journey can be built with or without a buying group, but the level of precision and impact changes significantly:<ul><li>**Without a buying group**, journeys are typically built around accounts. Marketers can still use signals like intent, behavior, or product interest to trigger nurture flows and outreach. This method works for simpler motions or when you have limited data about an account. However, it risks overlooking the broader set of stakeholders who influence the deal, which can slow down conversion or cause gaps in engagement.<li>**With a buying group**, journeys are orchestrated around the full set of personas involved in a purchase decision. You can align steps to group-level milestones (such as when the committee reaches a completeness score or shows collective engagement), while also personalizing touchpoints for each role. This method allows you to design coordinated multi-threaded engagement: a decision-maker might receive strategic ROI content, while influencers receive product deep-dives, and sales is alerted when critical roles engage. By mapping both the individual and collective journey, marketers and sellers can accelerate consensus-building and move opportunities forward more efficiently. </ul>|
| Using opportunity data to detect persona | To give you the most accurate view of who is engaging and where their interests lie, the agent approaches persona ranking and product intent according to the following: <ul><li>Best case scenario: If you can provide data like _Opportunity Stage_, _Opportunity Close Date_, and a clear _Opportunity-to-Product Mapping_, the agent can confidently rank personas per product.<li>This ranking provides a precise understanding of engagement and interest across the account. </ul>But the agent knows that the data is not always complete, which is OK. It includes smart fallbacks to keep things moving:<ul><li>The agent analyzes the volume of activities, giving more weight to recent ones using time decay.<li>This weighting allows the agent to differentiate and rank personas, even without full opportunity data. </ul>When it comes to linking opportunities to products, here's how the agent handles it:<ul><li>_Ideal_: You provide or help the agent create the mapping table.<li>_If not available_: the agent uses fuzzy matching to connect the dots.<li>_No linkage at all_: The agent infers product intent based on recent activities prior to the close date.</ul>This layered approach ensures that the agent can still deliver meaningful insights, even when the data isn't perfect. |
| Opportunity analysis | The agent looks at historical opportunity data to understand which factors most strongly predict a win, and it uses three core dimensions to do that:<ol><li>Win rate: Shows how often deals are successfully closed when certain personas are involved. If accounts with a specific persona pattern (like a technical evaluator or a VP-level decision maker) tend to convert more often, the model gives higher weight to that pattern. This information is a percentage of total opportunities, such as opportunities that are closed or won.<li>Membership rate: Measures how frequently a persona type shows up across opportunities for a given product. If certain personas consistently appear in successful deals, it indicates that they play a critical role in the buying process.<li>Persona influence: Quantifies how much a given persona contributes to the outcome, not just whether they are present, but how their engagement or activity level correlates with wins.</ol>Together, these signals help infer which personas have the strongest impact on purchase outcomes, even when opportunity data is incomplete. Over time, it allows the system to surface high-impact personas and patterns that are most predictive of deal success, which then inform account intent, persona mapping, and buying group recommendations. |
| Intent | When someone visits a web page or clicks an email link related to a product, it is a signal that they are interested, and that is called _intent_.<br/><br/>The agent starts with a taxonomy, which is basically a list of the customer's products and the keywords that describe them. This information helps the agent to understand what each piece of content or interaction is about.<br/><br/>Next, the agent uses that taxonomy to label visitor activity, such as which keywords or products their actions relate to.<br/><br/>Then, the agent looks at how deeply someone engages, such as how many pages they visit or how often they interact. It uses this information to calculate their individual intent score for specific keywords, products, or product categories. It buckets each intent score into _High_, _Medium_, or _Low_ intent to indicate the interest strength. (Low intent: `<=0.2`, Medium intent: `0.2 < score <= 0.6`, High intent: `0.6 < score <= 1`)<br/><br/>Finally, the agent combines the intent scores of all people from the same company (account) to see the overall account-level intent, showing which products or topics that company seems most interested in. |
| Roles influencing a buying group | Each buying group is comprised of roles who contribute differently to the purchase decision, such as _Decision Maker_, _Influencer_, _Champion_, and _End User_. Each role has a varying degrees of impact.<br/><br/>Decision Makers hold the most influence and typically control budget approvals. Influencers shape evaluation and recommendations. Champions help build internal consensus, while End Users validate the product's fit.<br/><br/>By showing you these roles, the agent helps you understand who is driving the buying decision, where your engagement is strongest, and where coverage gaps might exist. This information enables you to focus on the roles that matter most for this product. |
| Persona or role coverage | For any given product, there is usually a set of key roles and personas that are known to influence the purchase (_N_ personas or roles).<br/><br/>For each account, the agent calculates coverage by checking how many of those _N_ roles are represented by at least one person within that account.<br/><br/>If all _N_ roles are present, the account has full coverage. If only some roles are represented, the coverage is partial.<br/><br/>In simple terms, role and persona coverage measure how complete your buying group is for a product, based on whether all the important decision-makers, influencers, and champions are included. |

## XDM data prerequisites

Audience Agent provides insights on accounts showing first-party intent for products and computes persona and roles based on the defined data. Ensure that the following prerequisite data is configured to use Audience Agent capabilities:

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
      <td>whether opportunity is won (binary)</td>
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
      <td>Only for reference/book keeping; Information about the campaign name</td>
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
      <td>Only for reference/book keeping; Information about the source ID for whom the email is targeted</td>
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
      <td>Only for reference/book keeping; Information of the source instance for whom the email is targeted</td>
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
      <td>Used to fetch the email content from the Marketo Engage data center; it is comprised of (SourceID@SourceInsatceID.SourceType)</td>
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
      <td>Only for reference/book keeping; Information about the type of the source or where the source originated from </td>
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
      <td>Information about the source origin for whom the email is targeted</td>
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
      <td>only for reference/book keeping</td>
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
      <td>Only for reference/book keeping; Information about the source ID for whom the email is targeted</td>
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
      <td>Only for reference/book keeping; Information about the source instance for whom the email was targeted</td>
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
      <td>Only for reference/book keeping; it is comprised of (SourceID@SourceInsatceID.SourceType)</td>
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
      <td>Only for reference/book keeping; Information for the type of the source or where the source originated from</td>
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
