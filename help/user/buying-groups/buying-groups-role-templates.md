---
title: Buying Group role templates
description: Learn about...
feature: Buying Groups
exl-id: 9206356e-e9cf-486c-8982-c7d893222413
---
# Buying Group role templates

< high-level overview -- What are role templates used for? Are there any things that I should have in place before creating a role template? >

## Access and browse role templates

1. In your Adobe Experience Platform home page, click Adobe Journey Optimizer B2B Edition.

1. On the left navigation, click **[!UICONTROL Buying groups]**.

1. In the Buying Groups page, select the **[!UICONTROL Roles Templates]** tab.

   ![Roles Templates tab](assets/roles-templates-tab.png){width="700" zoomable="yes"}

   The tab provides an inventory list of all existing roles templates. It provides information as _[!UICONTROL Name]_, _[!UICONTROL Status]_, _[!UICONTROL Creation date]_, _[!UICONTROL Created by]_, _[!UICONTROL Last update]_, _[!UICONTROL Last updated by]_, _[!UICONTROL Published on]_, and _[!UICONTROL Published by]_ in column format. 

   The list is sorted by the _[!UICONTROL Last update]_ column by default.

   The number of _live_ (published) roles templates is displayed at the top-right of the page. All roles templates have a status of `Draft` or `Live`.

1. To filter the list by name, use the search field at the top of the list.

   Enter the first few characters of the name to reduce the displayed list to the matching items. 

   ![Roles Templates filtering by search string](assets/roles-templates-search.png){width="700" zoomable="yes"}

## Create a roles template

1. From the _[!UICONTROL Roles Templates]_ tab, click **[!UICONTROL Create template]** at the top-right corner.

1. In the dialog, enter a unique **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional) for the template.

   ![Create Roles Template dialog](assets/roles-template-create-dialog.png){width="400"}

1. Add a rule for each role that you want to define for the template.

   For the Beta release, there are six roles: `Decision Maker`, `Influencer`, `Practitioner`, `Executive Steering Committee`, `Champion`, and `Other`.

   ![Buying group roles list](./assets/roles-template-create-roles-list.png){width="700" zoomable="yes"}

    * Choose a role from the list.
    * Click **[!UICONTROL Add Condition]**.

    * In the condition dialog, expand the list of **[!UICONTROL Person attributes]** and locate an attribute that you want to use to match the role. Drag it to the right and drop it in the filter space. 

       ![Roles template add condition drag attribute](assets/roles-template-role-attribute.png){width="700" zoomable="yes"}

    * Use the attribute to create a matching filter using one or more values. 
    
       In the following example, the Job title attribute is used to identify a match for Decicion Maker. Any value for title that starts with `Director` or `Sr Director` evaluates as true for the condition.

       ![Roles template condition example using job title](assets/roles-template-condition-example-job-title.png){width="700" zoomable="yes"}

    * If needed, add another attribute and condition to further refine the criteria for a match to the role.

    * Click **[!UICONTROL Done]**.

    For each additional role you want to include for the templae, click **[!UICONTROL Add another role]** and define one or more conditions to match for the role.

    ![Roles template with multiple roles defined](assets/roles-template-multiple-roles.png){width="700" zoomable="yes"}

1. If the template is ready for use, click **[!UICONTROL Publish]** at the top-right.

    When you publish the template, it is set to a Live status and is available to associate with a SOlution Interest. 

    Your changes are auto-saved in the Draft status. If you are not ready to publish the roles template, click the left (back) arrow at the top of the page and return to the Roles Templates list. 


< PM -- the Required for completion checkbox is not available to clear. Is this functional for Beta? >

<!-- Required for completion checkbox - select this for a role if it is required to calculate the completeness score. -->

## Edit the rules for a draft roles template

Edit rules for each role.

Delete role card.

Priority - to re-order the roles and assign leads based on priority.
Actions - Delete, Publish.
Delete - can delete a role template only in draft status.
Publish - updates status to Live. At least 1 role is required to be added to Publish a role template.
