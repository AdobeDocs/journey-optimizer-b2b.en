---
title: Create and Publish Landing Pages
description: Create, design, and publish landing pages for journeys - build from scratch, import HTML, add forms, personalize content, and link from emails in Journey Optimizer B2B Edition.
feature: Landing Pages, Content
role: User
---
# Create and publish landing pages

As a marketer, you can define and publish pages that you want to incorporate into your account and people journeys. WHen you add a new landing page, you configure the primary page and any subpages, design the content, test it, and publish it.

![Landing page work flow diagram](./assets/landing-page-work-flow-diagram-no-subpages.svg)

>[!BEGINSHADEBOX]

## Landing page prerequisites

Before marketers can create landing pages to support their journeys and campaigns, the following configurations and assets must be in place:

* [Landing page subdomain](../admin/configure-channels-landing-pages.md#subdomains) - Set up a subdomain dedicated to hosting your landing pages.
* [Landing page preset](../admin/configure-channels-landing-pages.md#presets) - A preset defines the subdomain and other settings applied to your landing pages.
* [Form](./forms.md) (for data capture use cases) - Required when you want to embed a form on a landing page and submit data to Experience Platform.
<!-- * Subscription list (for subscription use cases) - Required if you want customers to subscribe to or unsubscribe from a specific service. This is in AJO B2C-->

>[!ENDSHADEBOX]

## Create a landing page {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b_lp_create"
>title="Define and configure your landing page"
>abstract="To create a landing page, you need to select a preset, then configure the primary page and subpages, and finally test your page before publishing it."

1. Go to the left navigation and select **[!UICONTROL Content Management]** > **[!UICONTROL Landing pages]**.

1. Click **[!UICONTROL Create landing page]** at the top right.

1. On the page, enter a useful **[!UICONTROL Title]** (required) and **[!UICONTROL Description]** (optional).

   Title and description criteria:

   * Title - Maximum of 100 characters, must be unique, case-insensitive

   * Description - Maximum of 300 characters

   * Alpha, numeric, and special characters are allowed

   * Reserved characters are **_not allowed_**: `\ / : * ? " < > |`

   ![Create landing page](./assets/landing-page-create.png){width="600"}

1. Select a **[!UICONTROL Preset]**.

   A product administrator [configures a preset](../admin/configure-channels-landing-pages.md#presets) to define the subdomain and other settings used for landing pages. You can select a preset and then click **[!UICONTROL View preset]** to open the preset details and check the settings to make sure that it matches with your landing page requirements.

1. Click **[!UICONTROL Create]**.

1. The primary page and its properties display. Learn how to configure the primary page settings [here](#configure-primary-page).

    ![New landing page - primary page properties](assets/lp_primary-page.png)

### Configure the primary page {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b_lp_primary_page"
>title="Define your primary page settings"
>abstract="The primary page is immediately displayed to the users after they click the link to your landing page, such as from an email or a website."

>[!CONTEXTUALHELP]
>id="ajo-b2b_lp_access_settings"
>title="Define your landing page URL"
>abstract="In this section, define a unique landing page URL. The first part of the URL requires you previously set up a landing page subdomain as part of the preset you selected."

1. Change the **[!UICONTROL Page Name]** according to your needs, which is _Primary page_ by default.

1. Define the ending portion of the page URL. 

    The first part of the URL is determined by the preset you selected.

    >[!CAUTION]
    >
    >The landing page URL must be unique.
    >
    >You cannot access your landing page by simply copy-pasting this URL into a web browser, even if published. Test it using the preview function.

    ![](assets/lp_access-url.png)

1. Set the **[!UICONTROL Page expiry]**.

   After you select an expiry date, choose the action upon page expiration:

    * **[!UICONTROL Redirect URL]** - Enter the URL of the page to use as a redirect.
    <!-- * **[!UICONTROL Custom page]** - Configure a subpage and select it from the list. -->
    * **[!UICONTROL Browser error]** - Enter the error text to display in place of the page.

1. To add the _[!UICONTROL Content]_ for the page, click **[!UICONTROL Open Designer]**.

    The _[!UICONTROL Create your primary landing page]_ home page loads and the design process begins with choosing the design type.

## Choose the design type 

The _[!UICONTROL Create your primary landing page]_ home page provides multiple options for creating the page: _[!UICONTROL Design from scratch]_, _[!UICONTROL Code your own]_, _[!UICONTROL Import HTML]_, or use a landing page template.
   
![Choose how you want to start your landing page design](./assets/landing-page-create-design.png){width="800" zoomable="yes"}
   
After you select the method that you want to use to start landing page design, use the visual design tools to [design the page](./landing-page-design.md).

### Design from scratch
   
Use the visual content editor to define the structure of the landing page content. By adding and moving structural components with simple drag-and-drop actions, you can design the shape of the page content within seconds.
   
1. From the _[!UICONTROL Create your primary landing page]_ home page, select the **[!UICONTROL Design from scratch]** option.

1. Choose how you want to manage styling for the page content:

    * **[!UICONTROL Use Themes]** - Choose this option to create the page content in _Theme mode_. In this mode, you can use a defined [brand theme](./brand-themes.md) to streamline the content authoring process and make sure that the design aligns with defined standards.

    * **[!UICONTROL Manual Styling]** - Choose this option to create the page content in _Manual mode_. In this mode, you manually set the styling for all structure and content components that you add to the blank canvas.

1. Click **[!UICONTROL Confirm]**.
   
1. [Add structure and content](./landing-page-design.md#add-structure-and-content) to the page.

### Code your own

_Code your own_ lets you write or paste raw HTML to build the page content directly in the design space. Use this mode when you need full control over markup. Using this mode requires that yuo have HTML skills.

After you choose this mode, you stay in the code editor; you cannot switch to the visual editor.

1. From the _[!UICONTROL Create your primary landing page]_ home page, select the **[!UICONTROL Code your own]** option.
   
1. Enter or paste your raw HTML code.

If you want to clear your page content and start from a new design, select **[!UICONTROL Change your design]** from the options menu.
   
### Import HTML
   
Adobe Journey Optimizer B2B Edition allows you to import existing HTML content to design your landing pages.
   
{{$include /help/_includes/content-design-import.md}}
   
![import html content in a zip file](./assets/templates-import-zip-file.png){width="500"}  
   
>[!NOTE]
>
>Using a `<table>` tag as the first layer in an HTML file can cause style loss, including background and width settings in the top layer tag.
   
You can personalize the imported content as needed with the visual design space.

### Select a saved or sample template
   
If you want to use a temples, you can choose from:

* **Sample templates**. The Journey Optimizer B2B Edition interface offers a collection of out-of-the-box landing page templates that you can use as a starting point for your landing page design.

* **Saved templates**. Use a saved custom template created by a member of your organization using the _[!UICONTROL Templates]_ menu <!-- or the _[!UICONTROL Save as content template]_ option when designing a landing page. -->

 Use the _[!UICONTROL Select design template]_ section to start building your content from a template. You can use a sample template or a saved custom landing page template from your Journey Optimizer B2B Edition instance.
   
>[!BEGINTABS]
   
>[!TAB Saved templates]

On the _Create your primary landing page_ home page, the _Sample templates_ tab is displayed by default. To use a custom template, select the **[!UICONTROL Saved templates]** tab.

The list of all saved landing page templates is displayed. You can sort them by _[!UICONTROL Name]_, _[!UICONTROL Last modified]_, and _[!UICONTROL Last created]_.

![Choose a saved template](./assets/landing-page-design-saved-templates-sort-by.png){width="700" zoomable="yes"}

Select a template thumbnail to display a preview. In preview mode, you can navigate between all the templates of one category (sample or saved, depending on your selection) using the right and left arrows.

![Preview the saved template](./assets/landing-page-design-saved-template-preview.png){width="800" zoomable="yes"}

When the display matches what you want to use, click **[!UICONTROL Use this template]** at the top right of the preview window.

This action copies the content into the visual design space, where you can edit the content as needed.
   
>[!TAB Sample templates]

Adobe Journey Optimizer B2B Edition offers a selection of _out-of-the-box_ landing page templates, which can be used for creating your own landing pages and landing page templates.
   
<!-- ![Choose a sample template provided by Adobe](../assets/content-design-shared/templates-design-samples.png){width="800" zoomable="yes"} -->

>[!ENDTABS]
   
<!-- 
>[!NOTE]
>
>Saved templates may have governance (content locking) settings applied to one or more components. The design tools provide guidelines about locked components when you [author content from a governed template](./email-authoring-governance.md). -->

## Check alerts

As you design your landing page content, alerts appear at the top right when key settings are missing.

![Alerts for page content issues](./assets/alerts-button.png){width="250"}

If you do not see this button, there are no detected issues.

There are two types of alerts:

* **_Warnings_** that refer to recommendations and best practices, such as:

   * `Placeholder links are present in the landing page body`: Do not forget to replace the placeholders with valid links.

   * `Text version of HTML is empty`: Do not forget to define a text version of your page body, which is used when HTML content cannot be displayed.

   * `Empty link is present in page body`: Check that all the links in your page are correct. 

* **_Errors_** that prevent you from testing or activating the journey/campaign as long as they are not resolved, such as:

   * `The landing page content is empty`: Page content is mandatory.

## Publish the page {#publish-landing-page}

When the draft page meets your criteria and you want to make the page available to link from journeys, click **[!UICONTROL Publish]**.

>[!CAUTION]
>
>* To publish landing pages, you must have the **[!UICONTROL Publish Messages]** permission.
>* Before publishing, check and resolve all alerts. [Learn more](#check-alerts)

![](assets/lp_publish.png)

Once your landing page is published, it is added to the landing page list with the **[!UICONTROL Published]** status.

It is now live and ready to be used in a [!DNL Journey Optimizer] message that will be sent through a [journey](../building-journeys/journey.md).

>[!NOTE]
>
>You cannot access your landing page by simply copy-pasting into a web browser the URL defined when [creating the page](#create-landing-page), even if published. Instead you can test it using the preview function such as described in [this section](#test-landing-page).

You can monitor your landing page impacts through specific reports. [Learn more](../reports/lp-report-live.md)
