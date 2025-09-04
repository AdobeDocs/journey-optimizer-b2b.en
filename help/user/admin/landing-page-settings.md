---
title: Landing page configuration
description: Learn how to access and configure the landing page settings so that your Marketing team can author and publish web pages to support their campaigns.
feature: Setup, Landing Pages, Content
role: Admin
hide: yes
hidefromtoc: yes
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
exl-id: 54b812cb-0129-4253-8e9e-538c25fc4709
---
# Landing page configuration

Administrators should ensure that the landing page settings are configured for Marketers who author and publish these pages. 

## Settings

To review the landing page configuration, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Landing Pages]_ in the navigation panel, select **[!UICONTROL Settings]**.

![Landing page settings](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

### Account string {#account-string}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_account_string"
>title="Landing pages account string"
>abstract="The account string identifies the Adobe Journey Optimizer B2B Edition instance that is hosting the landing pages."

The account string identifies the Adobe Journey Optimizer B2B Edition instance that is hosting the landing pages. Make sure that your Systems team adds and configures the DNS entry.

### Form prefill {#form-prefill}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_form_prefill"
>title="Landing page form prefill settings"
>abstract="You can enable the form prefill option to allow forms within your landing pages to use prefilled information for known users."

Enable the **[!UICONTROL Form prefill]** option to allow forms within your landing pages to use prefilled information for known users. When this option is disabled, landing page authors cannot include prefilled form fields.

### Datastream {#datastream}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_datastream"
>title="Datastream requirement"
>abstract="Datastream is needed to collect page events from the landing pages on this domain."

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_missing_datastream"
>title="Missing Datastream ID"
>abstract="The subdomian is missing a Datastream ID, which is required for proper routing. Configure it in Settings to continue"

Set the **[!UICONTROL Datastream]** option to configure a datastream for landing page event collection. 

## Subdomains {#add-subdomain}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_add_subdomain"
>title="Add landing page subdomain"
>abstract="You can add a maximum of 50 subdomains. Set up a new subdomain for each unique brand URL that you want to host on Adobe Journey Optimizer B2B Edition."

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_configure_subdomain"
>title="Configure landing page subdomain"
>abstract="A configured subdomain is required to publish landing pages. You can use a subdomain that is already delegated to Adobe or create a new subdomain."

A landing page subdomain should help to identify the content type, product name, or campaign, and reinforce the page authenticity. Before you configure the subdomains, define one or more CNAMEs to use for your landing pages. For example:

* **product**.[CompanyDomain].com
* **go**.[CompanyDomain].com
* **signup**.[CompanyDomain].com

In these examples, the first part (in bold) is the `LandingPageCNAME`.

Add a new subdomain for each unique brand URL that you want to host on Adobe Journey Optimizer B2B Edition. You can add a maximum number of 50 subdomains.

>[!IMPORTANT]
>
>Delegating an invalid subdomain to Adobe is not allowed. Make sure you enter a valid subdomain that your organization owns, such as _marketing.yourcompany.com_.

To review your subdomains and add new ones, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Landing Pages]_ in the navigation panel, select **[!UICONTROL Subdomains]**.

![Landing page subdomains](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

_To add a landing page subdomain:_

1. Click **[!UICONTROL Add subdomain]** at the top right.

1. In the _[!UICONTROL Subdomain details]_, enter the subdomain information:

   * **[!UICONTROL Subdomain]** - The subdomain URL to use, such as `marketing.yourcompany.com`
   * **[!UICONTROL Default page]** - The URL for the default subdomain page, such as `marketing.yourcompany.com/products`
   * **[!UICONTROL Fallback page]** - The URL for the fallback page to be used if a landing page on the subdomain is not active, such as `marketing.yourcompany.com/expired`

   ![Add landing page subdomain](./assets/config-landing-pages-add-subdomain.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.
