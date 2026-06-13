---
title: Landing Pages
description: Create, design, and publish landing pages for person journeys - build from scratch, import HTML, add forms, personalize content, and link from emails in Journey Optimizer B2B Prime.
autotag-review: '2026-06-12T22:53:39.337Z'
TQID: 'https://experienceleague.adobe.com/BvtB0i5CzlVutPA6HAzZy-Gfymw7ppZwthyBauyciLc'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
    internal-label: Content management
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: a96755d6-1f54-4f3f-a971-d31f83705ab7
    internal-label: Landing pages
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Landing pages

A landing page is a standalone web page where you can direct contacts and customers after they click a linked item in an email, SMS message, or any digital location. You can incorporate these pages into your journeys to get your prospects and customers to view your messages on the web and progress along in your journeys. You can create, personalize, and preview landing pages in the landing page visual design space.

Common use cases for landing pages:

* Provide opt in or opt out of marketing communications or a specific service. Use  a link in an email or other communication to a targeted list.
* Collect consent before sending communications and send a confirmation email upon opt-in or opt-out.
* Capture or update profile data (progressive profiling, preferences, registrations, and similar scenarios) using forms on landing pages.
* Direct people to campaign-specific information designed for your journey orchestration.
* Redirect people to a dedicated web form without building an external page outside of Journey Optimizer B2B Prime.

<!-- 
## Landing page workflow

To direct members of a journey audience to a defined web page when they click a specific link, create a landing page in Journey Optimizer B2B Edition: 


1. [Create the page](./landing-pages-create-publish.md) - Select a preset, set up the primary page, and add any required subpages.
1. [Design the landing page content](./landing-page-design.md) - Build the page content using drag-and-drop visual design components.
1. [Test the landing page](./landing-pages-create.md) - Preview the page, test form behavior, and then publish to make it live.
1. [Link to the page from your journey](#link-to-a-landing-page) - Add the landing page URL to an email, SMS, or journey action so that recipients can reach it.


For example, you can create and design landing pages to direct your users to online information. The page could include a form where they can opt in or opt out from receiving your communications. Or it could be an opportunity to subscribe to a recurring communications, such as a newsletter. 

You can create, personalize, and preview landing pages in the visual design space.
-->
## Access and manage landing pages {#access-manage-landing-pages}

To access landing pages in Journey Optimizer B2B Prime, go to the left navigation and click **[!UICONTROL Content Management]** > **[!UICONTROL Landing pages]**. This action displays a list of all landing pages created in the instance.

The list is sorted according to the _[!UICONTROL Modified]_ column, with the most recently updated items at the top. Click the column title to change between ascending and descending.

### Filter the landing pages list {#filter-list}

To search for a landing page by name, enter a text string into the search bar for a match. Click the _Filter_ icon <!-- ( ![Show or hide filters icon](../assets/do-not-localize/icon-filter.svg) ) --> to show the available filter options and change the settings to filter the displayed items according to your specified criteria.

![Filter the displayed landing pages](./assets/landing-pages-list-filtered.png){width="800" zoomable="yes"}

<!-- 
This is going away? ### Customize the column display

Customize the columns that you want to display in the table by clicking the _Customize table_ icon ( ![Customize table icon](../assets/do-not-localize/icon-column-settings.svg) ) at the top right. 

In the dialog, select the columns to display and click **[!UICONTROL Apply]**.

![Select the columns that you want to display](./assets/landing-pages-customize-table-dialog.png){width="300"} 
-->

### Landing page status and lifecycle {#landing-page-status}

The landing page status determines its availability for linking in your email and SMS content, and the changes that you can make to it. 

| Status               | Description |
| -------------------- | ----------- |
| Draft                | When you create a landing page, it is in draft status. It remains in this status as you define or edit the visual content and until you publish it as a hosted page. Available actions:<br/><ul><li>Edit name or description</li><li>Edit link URL</li><li>Edit in visual design space</li><li>Publish</li><li>Duplicate</li><li>Delete</li></ul> |
| Published            | When you publish a landing page, it is hosted on the Journey Optimizer B2B Prime instance and it becomes available for linking in an email or SMS message content. Available actions:<br/><ul><li>Edit name or description</li><li>Edit link URL</li><li>Add link in email or SMS message content</li><li>Create draft version</li><li>Duplicate</li><li>Delete</li></ul> |
| Published with draft | When you create a draft from a published landing page, the published version remains, and the draft content can be modified in the visual design space. If you publish the draft version, it replaces the current published version and the content is updated in the hosted page. Available actions:<br/><ul><li>Edit name or description</li><li>Edit link URL</li><li>Add link in email or SMS message content</li><li>Edit draft version in visual design space</li><li>Publish draft version</li><li>Duplicate</li><li>Delete (deletes both versions)</li><li>Discard draft (returns to published status)</li></ul> |

<!-- ![Landing page status lifecycle](./assets/status-lifecycle-diagram.png){zoomable="yes"} -->

## Create a landing page {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_create"
>title="Define and configure your landing page"
>abstract="To create a landing page, you need to select a preset, then configure the primary page and subpages, and finally test your page before publishing it."

To direct members of a person journey audience to a defined web page when they click a specific link, create a landing page in [!DNL Journey Optimizer B2B Prime]. You select a preset, configure the primary page and any subpages, [test the page](#test-landing-page), and publish it.

>[!IMPORTANT]
>
>Before you create your first landing page, complete the landing page setup. This includes configuring a subdomain to host your landing pages and defining at least one preset that specifies the subdomain and other channel settings. You select a preset when you create the landing page. For administrator setup, see [Landing page configuration](../admin/configuration-presets-landing-pages.md).
>
>For data capture use cases, create a [form](./forms.md) before you embed it on a landing page.

To create a landing page, follow these steps:

1. Go to the left navigation and select **[!UICONTROL Content Management]** > **[!UICONTROL Landing pages]**.

1. From the landing page list, click **[!UICONTROL Create landing page]**.

1. Enter a **[!UICONTROL Title]** (required) and **[!UICONTROL Description]** (optional).

   Title and description criteria:

   * **Title** — Maximum of 100 characters. Must be unique (case-insensitive).
   * **Description** — Maximum of 300 characters.
   * Alpha, numeric, and special characters are allowed.
   * Reserved characters are **_not allowed_**: `\ / : * ? " < > |`

1. Select a **[!UICONTROL Preset]**.

   An administrator [creates landing page presets](../admin/configuration-presets-landing-pages.md#lp-presets) to define the subdomain and other settings used for landing pages. Select a preset, then click **[!UICONTROL View preset]** to review its settings and confirm they match your landing page requirements.

1. Click **[!UICONTROL Create]**.

   The primary page and its properties are displayed. Learn how to [configure the primary page settings](#configure-primary-page).

1. To add a subpage (for example, a thank-you or error page), click the **+** icon.

   You can add up to two subpages per landing page.

Once you configure and design the primary page and any subpages, [test your landing page](#test-landing-page) before you publish it.

>[!CAUTION]
>
>You cannot access your landing page by copying and pasting the defined URL into a web browser, even if the page is published. Test the page using the preview function as described in [Test the landing page](#test-landing-page).

## Configure the primary page {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_primary_page"
>title="Define your primary page settings"
>abstract="Define the primary page, which is immediately displayed when a recipient clicks the landing page link, such as from an email or a website."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_access_settings"
>title="Define your landing page URL"
>abstract="In this section, define a unique landing page URL. The first part of the URL requires that you previously set up a landing page subdomain as part of the preset you selected."

The primary page is the page that is immediately displayed when a recipient clicks the landing page link, such as from an email or a website.

To define the primary page settings, follow these steps:

1. Change the **[!UICONTROL Page Name]** according to your needs, which is _Primary page_ by default.

1. Define the ending portion of the page URL.

   The preset that you selected determines the first part of the URL. An administrator configures the [landing page subdomain](../admin/configuration-presets-landing-pages.md#lp-subdomains) as part of the preset.

   >[!CAUTION]
   >
   >The landing page URL must be unique.
   >
   >You cannot access your landing page by copying and pasting this URL into a web browser, even if the page is published. Test it using the preview function as described in [Test the landing page](#test-landing-page).

1. If you want an anonymous landing page, disable the **[!UICONTROL Require identified users]** option.

1. Click the _Calendar_ icon to set the **[!UICONTROL Page expiry]**.

   After you select an expiry date, choose the action upon page expiration:

   * **[!UICONTROL Redirect URL]** - Enter the URL of the page to use as a redirect.
   * **[!UICONTROL Browser error]** - Enter the error text to display in place of the page.

## Test the landing page {#test-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_preview_lp_profiles"
>title="Preview and test your landing page"
>abstract="After you define your landing page settings and content, use test profiles to preview the page."

When the landing page settings and content are defined, you can use test profiles to preview the page. If you inserted [personalized content](email-authoring.md#personalization), you can check how this content is displayed in the landing page using test profile data.

>[!PREREQUISITES]
>
>To preview and test landing pages, you must have the **[!UICONTROL Publish Messages]** permission and a defined dataset that contains test profiles.

1. Click **[!UICONTROL Preview & test]** to open the test profile selection.

   >[!NOTE]
   >
   >You can also use **[!UICONTROL Simulate content]** when you are in the visual design space.

1. From the _[!UICONTROL Simulate]_ screen, select a test profile.

   If the profiles that you need are not listed, click **[!UICONTROL Manage test profiles]** to use a known test profile email address and add it to the list.

   +++Add test profiles

   For **[!UICONTROL Identity namespace]**, click the _Select_ icon <!-- ( ![Select icon](../assets/do-not-localize/icon-select-data.svg) ) --> and choose the `Email` namespace to use to test profiles.

   In the **[!UICONTROL Identity value]** field, enter the email address to identify the test profile and click **[!UICONTROL Add profile]**. You can repeat this to add multiple profiles.

   Click the back arrow at the top left to return to the _[!UICONTROL Simulate]_ page.

   +++

1. Select **[!UICONTROL Open preview]** to test your landing page.

   The landing page preview opens in a new tab. The selected test profile data replaces personalized elements.

1. Select other test profiles to preview the rendering for each variant of your landing page.

## Edit a landing page {#edit-landing-page}

Edits to a landing page depend on its current status:

* When a landing page is in **_Draft_** status, you can edit any of its details, the URL, and the visual content.
* When a landing page is in **_Published_** status, you can edit the description, but not the name. To change the visual content, you must create a draft version of the page.
* When a landing page is in **_Published with draft_** status, editing the details is limited to the description. You can also edit the visual content for the draft version.

>[!BEGINTABS]

>[!TAB Draft]

1. From the _[!UICONTROL Landing pages]_ listing page, click the landing page name to open it.

   A preview of the visual content is displayed, with the landing page details on the right.

1. Modify any of the details, such as name and description.

   <!-- ![Details for landing page with Draft status](./assets/landing-page-draft-details.png){width="700" zoomable="yes"} -->

1. To make changes to the content in the visual design space, click **[!UICONTROL Edit landing page]**.

   <!-- 
   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)
   -->

1. Click **[!UICONTROL Save]**, or **[!UICONTROL Save & close]** to return to the landing page details.

1. When the page meets your criteria and you want to make it available for display, click **[!UICONTROL Publish]**.

>[!TAB Published]

1. From the _[!UICONTROL Landing pages]_ listing page, click the page name to open it.

   A preview of the visual content is displayed, with the landing page details on the right.

1. Modify the description, if needed.

   For a published landing page, all other details cannot be changed.

1. If you want to update the content, click **[!UICONTROL Edit landing page]** on the right.

   Click **[!UICONTROL Create draft version]** in the dialog to open the draft version in the visual design space.

   <!-- 
   ![Create draft version dialog](./assets/landing-page-create-draft-version.png){width="300"} 

   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)
   -->

1. Click **[!UICONTROL Save]**, or **[!UICONTROL Save & close]** to return to the landing page details.

1. When the draft landing page meets your criteria and you want to make the changes available on the published page, click **[!UICONTROL Publish]**.

   When you publish the draft version, it replaces the current published version and the content is updated for the page URL.

>[!TAB Published with draft]

When you open the landing page, the draft version is displayed. The tabs at the top of the preview space allow you to toggle the display between the published and draft versions. The draft actions and details are displayed on the right. 

<!-- ![Preview and details for the landing page draft version](./assets/landing-page-published-draft-details.png){width="700" zoomable="yes"} -->

To update the content:

1. Click **[!UICONTROL Edit landing page]** at the top right.

   <!--

   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)

   -->

1. Click **[!UICONTROL Save]**, or **[!UICONTROL Save & close]** to return to the landing page details.

1. When the draft page meets your criteria and you want to make the changes available, click **[!UICONTROL Publish]**.

   When you publish the draft version, it replaces the current published version and the content is updated in the hosted page.

>[!ENDTABS]

## Duplicate a landing page {#duplicate-landing-page}

You can duplicate a landing page using either of the following methods:

* From the _[!UICONTROL Landing page]_ listing page, click the _More_ icon (**...**) next to the landing page name and choose **[!UICONTROL Duplicate]**.
* At the top right of the landing page details page, click **[!UICONTROL ... More]** and choose **[!UICONTROL Duplicate]**.

<!-- ![Duplicate the landing page](./assets/landing-page-details-duplicate-delete.png){width="600" zoomable="yes"} -->

In the dialog, enter a useful name (unique) and description (optional). Click **[!UICONTROL Duplicate]** to complete the action.

<!-- ![Enter a name and description for the duplicated landing page](./assets/landing-page-duplicate-dialog.png){width="350"} -->

The duplicated (new) page then appears in the _Landing pages_ listing.

## Delete a landing page {#delete-landing-page}

You can delete a landing page using either of the following methods:

* From the _[!UICONTROL Landing page]_ listing page, click the _More_ icon (**...**) next to the landing page name and choose **[!UICONTROL Delete]**.
* At the top right of the landing page details page, click **[!UICONTROL ... More]** and choose **[!UICONTROL Delete]**.

This action opens a confirmation dialog. You can abort the process by clicking **[!UICONTROL Cancel]**, or click **[!UICONTROL Delete]** to confirm deletion.

<!-- ![Delete landing page dialog](./assets/landing-page-delete-dialog.png){width="400"} -->

## Link to a landing page {#link-to-landing-page}

As a marketer or creative that produces email, fragment, and page content, you can embed links to the published (live) landing pages that are created in your Journey Optimizer B2B Prime instance.

1. As you work in the visual design space for a fragment, email, landing page, or template, select an excerpt of text, a button component, or an image component for the link.

   The **[!UICONTROL Link]** options are displayed in the right panel.

1. For the **[!UICONTROL Type]** option, choose **[!UICONTROL Landing page]**.

   <!-- ![Link options for a landing page](/help/assets/content-design-shared/content-design-link-settings.png){width="700" zoomable="yes"} -->

1. For the **[!UICONTROL Landing page]** option, click the _Select page_ icon <!-- ( ![Show links icon](/help/assets/do-not-localize/icon-landing-page-select.svg) ) -->.

1. In the Select landing page dialog, set the **[!UICONTROL Landing page source]** as **[!UICONTROL Journey Optimizer B2B Edition]**, select the checkbox for the landing page from the list of published pages, and click **[!UICONTROL Select]**.

   <!-- ![Link options for a landing page](/help/assets/content-design-shared/content-design-link-landing-page-select.png){width="600" zoomable="yes"} -->

1. For the **[!UICONTROL Target]** option, choose the link target behavior:

   * **[!UICONTROL None]** - Opens the link using the browser default behavior.
   * **[!UICONTROL Blank]** - Opens the link in a new window or tab.
   * **[!UICONTROL Self]** - Opens the link in the same frame.
   * **[!UICONTROL Parent]** - Opens the link in the parent frame.
   * **[!UICONTROL Top]** - Opens the link in the full body of the window.

1. (Text link only) If you want to underline the linked text, select the **[!UICONTROL Underline link]** checkbox.

   You can set additional styling for the link text, including the link color, by selecting the **[!UICONTROL Styles]** tab in the right panel.
