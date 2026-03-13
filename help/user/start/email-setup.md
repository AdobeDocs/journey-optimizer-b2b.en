---
title: Email Setup
description: Placeholder
feature: Setup, Channels
role: Admin
---
# Email setup

To support the email delivery infrastructure provided by the attached Marketo Egage instance, set the following email options. A Marketo Engage product administrator can configure these settings by navigating to the **[!UICONTROL Admin]** area in the Marketo Engage instance and selecting **[!UICONTROL Email]**.

## Email settings

To setup email default values for the attached Marketo Engage instance, change the configured values to reflect usage by your marketing organization.

### From email and label

Change the values for the From email and label so that new emails are automatically populated with these default values.

>[!NOTE]
>
>The change is only applicable to the emails that you create and not to other Marketo Engage or Journey Optimizer B2B Edition users.

1. Go to the **[!UICONTROL Admin]** area in the attached Marketo Engage instance and select **[!UICONTROL Email]**.

1. In the _[!UICONTROL Settings]_ panel, enter the default values you want for **[!UICONTROL From Email]** and **[!UICONTROL From Label]**.

   ![Email settings - From Email and From label default values](./assets/me-admin-email-settings-from.png){width="500"}

1. Click **[!UICONTROL Save Changes]**.

### Unsubscribe messaging

For non-operational marketing emails, unsubscribe text and links are appended at the bottom. As a product administrator, you should configure the default HTML and text that is populated when a marketer does not mark the email as operational.

1. Go to the **[!UICONTROL Admin]** area in the attached Marketo Engage instance and select **[!UICONTROL Email]**.

1. In the _[!UICONTROL Settings]_ panel, enter the default values you want for **[!UICONTROL Unsubscribe HTML]** and **[!UICONTROL Unsubscribe Text]**.

   >[!TIP]
   >
   >Marketers can change the position of the unsubscribe HTML in their email using system tokens.

   ![Email settings - Unsubscribe HTML and Unsubscribe Text default values](./assets/me-admin-email-settings-unsubscribe.png){width="500"}

   >[!CAUTION]
   >
   >The following variables are critical. **Do not delete** them.
   >
   >* `%mkt_opt_out_prefix%`
   >* `mkt_unsubscribe=1&mkt_tok=##MKT_TOK##`

1. Click **[!UICONTROL Save Changes]**.

If you ever need to revert to default system content, copy and paste the following:

+++ System default Unsubscribe Text

```
<p><font face="Verdana" size="1">If you no longer wish to receive these emails, click on the following link: <a href="%mkt_opt_out_prefix%UnsubscribePage.html?mkt_unsubscribe=1&mkt_tok=##MKT_TOK##">Unsubscribe</a><br/></font></p>` [!UICONTROL Unsubscribe Text]:
%mkt_opt_out_prefix%UnsubscribePage.html?mkt_unsubscribe=1&mkt_tok=##MKT_TOK##
```

+++

### View as web page

Email content has limited display capabilities (limited CSS and no JavaScript or forms). Marketers can use _View as Web Page_ option applies a cookie for he email recipient using the Marketo Munchkin. As a product administrator, you should configure the default HTML and text that is populated when a marketer chooses this option.

1. Go to the **[!UICONTROL Admin]** area in the attached Marketo Engage instance and select **[!UICONTROL Email]**.

1. In the _[!UICONTROL Settings]_ panel, change the content in the **[!UICONTROL View as Web Page HTML]** and **[!UICONTROL View as Web Page Text]** fields to reflect your tone and messaging.

   ![Email settings - View as Web Page HTML and View as Web Page Text default values](./assets/me-admin-email-settings-view-as-web-page.png){width="500"}

   >[!CAUTION]
   >
   >The following variables are critical. **Do not delete** them.
   >
   >`%mkt_webview_url%?mkt_tok=##MKT_TOK##`
   >
   >The second part `##MKT_TOK##` is the Munchkin cookie of that person. It ensures that cookies are applied appropriately when the email recipient clicks the link.
   >
   >Be sure to avoid:
   >
   >* Adding additional URLs to either of the HTML boxes
   >* Putting HTML in the text version

1. Click **[!UICONTROL Save Changes]**.

If you ever need to revert to default system content, copy and paste the following:

+++ System default web page HTML

```
<div style="text-align: center"><font face="Verdana" size="1">To view this email as a web page, <a href="%mkt_webview_url%?mkt_tok=##MKT_TOK##">click here</a></font></div>
```

+++

+++ System default web page text

```
To view this email as a web page, go to the following address:
`%mkt_webview_url%?mkt_tok=##MKT_TOK##`
```

+++

## Custom object retrieval limits

If you use [!DNL Velocity Script] to display custom object data in emails, adjust the parent custom object retrieval limit. By default, the limit allows access to 10 parent custom objects from Velocity Script. You can increase this limit if needed.

[[!DNL Apache Velocity]](https://velocity.apache.org/) is a language built on [!DNL Java] that is designed for templating and scripting HTML content. The Marketo Engage email infrastructure supports its use in the context of emails through scripting tokens, which provide access to data stored in custom objects.

You can reference parent and child custom objects that are directly connected to the lead, or contact, but not third-level custom objects. For each custom object, the 10 most recently updated records per person/contact are available at runtime and are ordered from most recently updated (at `0`) to oldest updated (at `9`).

_To change the limit:_

1. Go to the **[!UICONTROL Admin]** area in the attached Marketo Engage instance and select **[!UICONTROL Email]**.

1. Scroll to the _[!UICONTROL Custom Object Retrieval Limits]_ panel, and enter a new value in the **[!UICONTROL Parent Retrieval Limit]**
field.

   ![Marketo Engage email admin - Custom Object Retrieval Limits default values](./assets/me-admin-email-custom-object-retrieval-limits.png){width="500"}

   Values from 10 - 100 are supported. The _[!UICONTROL Child Retrieval Limit]_ is set automatically by dividing 1000 by the parent limit. For example, if you set the parent limit to 50, the child limit is calculated as 20 (1000 ÷ 50 = 20).

1. Click **[!UICONTROL Save Changes]**.

## Custom header options

Change the _[!UICONTROL Custom Header Options]_ for email to configure email tracking link headers. Enable these options to implement secure tracking links using HTTPS using Strict Transport.

1. Go to the **[!UICONTROL Admin]** area in the attached Marketo Engage instance and select **[!UICONTROL Email]**.

1. Scroll to the _[!UICONTROL Custom Header Options]_ panel, and change the setting according to your tracking link policies:

   ![Marketo Engage email admin - Custom Header Options default settings](./assets/me-admin-email-custom-object-retrieval-limits.png){width="500"}

   * **[!UICONTROL Strict Transport Security]** - Set this option to Enabled to guarantee that tracking links are always served over HTTPS (should only be set for subscriptions with tracking links secured by SSL). 
   * **[!UICONTROL Max-age]** - This field supports the mandatory directive to specify the time, in seconds, that the browser should remember to only access the domain over HTTPS.
   * **[!UICONTROL IncludeSubDomains]** - Use this option to include the directive that applies the HSTS policy to all subdomains of the host.

   >[!IMPORTANT]
   >
   >Review these settings with your IT team to make sure that they are aligned with your organization's policy. Incorrect settings can prevent some visitors from accessing your email links.

1. Click **[!UICONTROL Save Changes]**.

## Filter email bot activity {#filter-email-bots}

Email bot activity, also referred to as non-human interactions (NHI), can inflate your email _opens_ and _clicks_ data, distorting your engagement metrics and triggering event-based journey progression. Use email bot filtering to maintain the integrity of click engagement metrics and insights. There are two methods for identifying suspected bot activity:

* _**[!UICONTROL Match with IAB Bot list]**_ - Activities that match with anything on the [Interactive Advertising Bureau bot list](https://www.iab.com/guidelines/iab-abc-international-spiders-bots-list/){target="_blank"} (User Agent/IP address) are marked as bots.
* _**[!UICONTROL Match with Proximity Pattern]**_ - Two or more activities that happen at the same time (in under a second) are identified as bots. Attributes considered during comparison are:
  * Lead ID (should be the same)
  * Email asset (should be the same)
  * Link click or email open

For email link click and email open activity, attributes are populated with the following values:

* Activities that are identified as bots -  _Bot Activity_ = `true` and _Bot Activity Pattern_ = identified pattern/method
* Activities that are identified as not bots - _Bot Activity_ = `false` and _Bot Activity Pattern_ = `n/a`

### Set the filters

1. Go to the **[!UICONTROL Admin]** area in the attached Marketo Engage instance and select **[!UICONTROL Email]**.

1. Select the **[!UICONTROL Bot Activity]** tab.

   ![Marketo Engage email admin - Bot Activity tab](./assets/me-admin-email-bot-activity.png){width="700" zoomable="yes"}

   The Bot Activity Identification panel displays two sliders that you can use to identify bot activity.
   
1. Toggle the slider to enable one or both.

   For each method that you enable, choose _[!UICONTROL Log Bot Activity]_ or _[!UICONTROL Filter Bot Activity]_.

   >[!IMPORTANT]
   >
   >If you choose [!UICONTROL Filter Bot Activity], you may see a drop in email opens and clicks because false activities are eliminated.

   ![Marketo Engage email admin - Bot Activity Identification options](./assets/me-admin-email-bot-activity-set-filters.png){width="500"}

   For  _[!UICONTROL Match with Proximity Pattern]_, you can also set the amount of seconds for **[!UICONTROL Duration Between Activities]** (default is `0`, maximum is `3`).

   >[!NOTE]
   >
   >With _Duration Between Activities_ set to `0` seconds, Marketo Engage identifies email activities that are happening at the exact same second. If multiple email activities happen within the designated amount of seconds, it is identified as bot activity.

   To disable either filtering method, toggle the slider to the left. If you do, the data does not reset.

### IP Blocklist

Adobe has identified a list of IP addresses that are responsible for generating millions of fake engagements, as such engagement received from any of the following IPs is automatically filtered out and not added to your Marketo Engage instance. This filtering may result in a reduction in email opens, clicks, and other related activities. This list may be updated periodically.

+++ Blocked IP addresses

* 40.94.34.52
* 40.94.34.86
* 52.34.76.65
* 54.70.53.60
* 54.71.187.124
* 60.28.2.248
* 64.235.150.252
* 64.235.153.10
* 64.235.153.2
* 64.235.154.105
* 64.235.154.109
* 64.235.154.140
* 64.74.215.1
* 64.74.215.100
* 64.74.215.138
* 64.74.215.139
* 64.74.215.142
* 64.74.215.146
* 64.74.215.150
* 64.74.215.154
* 64.74.215.158
* 64.74.215.162
* 64.74.215.164
* 64.74.215.166
* 64.74.215.170
* 64.74.215.174
* 64.74.215.176
* 64.74.215.178
* 64.74.215.51
* 64.74.215.56
* 64.74.215.58
* 64.74.215.59
* 64.74.215.86
* 64.74.215.98
* 65.154.226.101
* 66.249.91.149
* 70.42.131.106
* 74.125.217.116
* 74.217.90.250
* 104.129.41.4
* 104.47.55.126
* 104.47.58.126
* 104.47.70.126
* 104.47.73.126
* 104.47.73.254
* 104.47.74.126
* 128.220.160.1
* 155.70.39.101
* 162.129.251.14
* 162.129.251.42
* 208.52.157.204

>[!NOTE]
>
>Every IP address is meticulously analyzed and scrutinized before it is included in this list, ensuring only the most critical and harmful IPs are blocked.

+++

