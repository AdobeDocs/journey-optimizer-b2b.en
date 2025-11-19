---
title: Activate Marketo Engage to Support Journey Actions
description: "Activate Marketo Engage connections to support journey actions so that marketers can coordinate campaigns between Marketo Engage and Journey Optimizer B2B Edition."
feature: Integrations, Audiences, Buying Groups
role: User, Admin
---

# Activate Marketo Engage instances to support actions

Marketo Engage actions are _people-based_ actions that allow you to coordinate your _account-based_ marketing orchestration between Journey Optimizer B2B Edition and your _lead-based_ marketing efforts in Marketo Engage. Use these actions to orchestrate static list membership and to place people into campaigns.

To use Marketo Engage actions, an administrator first creates a [custom service](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#) in Marketo Engage, which provides the credentials needed for authentication. 
Then, a product administrator for Journey Optimizer B2B Edition creates a connection to Marketo Engage by entering the credentials.
Journey Optimizer B2B Edition users can then reference the connection to configure Marketo Engage actions in <!-- Person and -->account journeys, such as adding or removing people from Marketo Engage lists or adding them to request campaigns.

Marketo Engage workspace visibility for assets, such as lists and campaigns, is governed by the role permissions assigned in the custom service.

The same connection can be used multiple times within a journey, and different Marketo Engage connections can coexist in a single journey.

When an action runs, it uses the Selection Policy to determine which person records in Marketo Engage to select if multiple identifiers exist in the unified person profile. Options include choosing the oldest, newest, or all matching Marketo Engage records. People proceed through the journey regardless of a match, except when an error occurs.

## Configure a Marketo Engage connection

Configure a remote Marketo Engage instance for use with Marketo Engage journey actions.

### Create the Marketo Engage custom service

1. Log in to Marketo Engage as an administrator and create a custom service.
1. Record the following values to use for the connection:

   * Munchkin ID
   * Client ID
   * Client Secret

### Add the integration

![Add integration details](assets/integration-connection-details.png)

1. In Journey Optimizer B2B Edition, navigate to **Administration** > **Configurations**.
1. Select to the **Integrations** tab.
1. Click **[!UICONTROL Create a connection]**.
1. Enter a name (required) and description (optional).
1. Select a **Selection policy** for matching person records.
1. Enter your Munchkin ID, Client ID, and Client Secret.
1. Click **[!UICONTROL Connect to Marketo]**.
1. Click **[!UICONTROL Create]**.

When a marketer uses a Marketo Engage action in a journey, they can configure the node using the connection name.

With the completed integration, Marketo Engage actions are available from **Actions on:** in the node properties.

![Marketo actions list](assets/marketo-actions-list.png)