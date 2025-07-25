---
title: Buying Group Role Templates
description: Learn about defining a role template to be used as a buying group component.
feature: Buying Groups
role: User
exl-id: 9206356e-e9cf-486c-8982-c7d893222413
---
# Buying group role templates

In a B2B market, buying decisions are usually made by multiple individuals. Those individuals participate in the decision-making process according to their role within the organization. Create Buying Group role templates that contain these role definitions according to each product offering type or account use case.

![Video](../../assets/do-not-localize/icon-video.svg){width="30"} [Watch the overview video](#overview-video)

## Access and browse role templates

1. On the left navigation, click **[!UICONTROL Buying groups]**.

1. In the _[!UICONTROL Buying groups]_ page, select the **[!UICONTROL Roles Templates]** tab.

   ![Roles Templates tab](assets/roles-templates-tab.png){width="700" zoomable="yes"}

   The tab provides an inventory list of all existing roles templates and displays the following information in column format:

   * [!UICONTROL Name]
   * [!UICONTROL Status]
   * [!UICONTROL Creation date]
   * [!UICONTROL Created by]
   * [!UICONTROL Last update]
   * [!UICONTROL Last updated by]
   * [!UICONTROL Published on]
   * [!UICONTROL Published by]

   The list is sorted by the _[!UICONTROL Last update]_ by default. All roles templates have a status of `Draft` or `Live`.

1. To filter the list by name, use the search field at the top of the list.

   Enter the first few characters of the name to reduce the displayed list to the matching items. 

   ![Roles Templates filtering by search string](assets/roles-templates-search.png){width="700" zoomable="yes"}

## Create a roles template

1. From the _[!UICONTROL Roles Templates]_ tab, click **[!UICONTROL Create template]** at the top-right corner.

1. In the dialog, enter a unique **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional) for the template.

   ![Create Roles Template dialog](assets/roles-template-create-dialog.png){width="400"}

1. Click **[!UICONTROL Create]**.

### Add the template roles

After you create the template, it opens in the workspace and you are prompted to define the roles. The first role card is displayed by default.

Each role that you define for the template uses a set of filters, or _conditions_, to determine the members assigned to the role. Use the following filter types to define the conditions for a role:

| Type | Condition |
| ---- | --------- |
| Person attributes | <li>Email address <li>Email invalid <li>Email suspended <li>Fax number <li>First name <li>Inferred state region <li>Job title <li>Last name <li>Middle name <li>Mobile phone number <li>Phone number <li>Postal code <li>State <li>Unsubscribed <li>Unsubscribed reason |
| Special filters | <li>Member of list <li>Member of program|
| Intent data | Category intent <li>Product intent <li>Keyword intent<br/>[Learn about intent data](../admin/intent-data.md).|

1. For the first role card, define the role properties.

   * Choose the **[!UICONTROL Buying group role]** from the list.

      For the current release, there are six roles: `Decision Maker`, `Influencer`, `Practitioner`, `Executive Steering Committee`, `Champion`, and `Other`.

      ![Buying group roles list](./assets/roles-template-create-roles-list.png){width="700" zoomable="yes"}  

   * Set the **[!UICONTROL Weighting]** for the role, which is used to calculate the engagement score. 

      The value for each option is translated to a percentage for the score calculation: [!UICONTROL Trivial] = 20, [!UICONTROL Minor] = 40, [!UICONTROL Normal] = 60, [!UICONTROL Important] =  80, and [!UICONTROL Vital] = 100.

      For example, a role template with roles using Vital, Important, and Normal, are then converted as 100/240, 80/240, 60/240.

   * **[!UICONTROL Add conditions for auto-assignment]** - Select this checkbox to add conditions for auto-assigning members to the buying group who match the condition. If the checkbox is not selected, then adding conditions is NOT required.

   * **[!UICONTROL Required for completeness score]** - Select this checkbox for the role if you want it to be a requirement for calculating a completeness score.

1. Click **[!UICONTROL Add Condition]** and define the conditional rule for the role.

   * In the _[!UICONTROL Condition]_ dialog, expand the list of **[!UICONTROL Person attributes]** and locate an attribute that you want to use to match the role. Drag it to the right and drop it in the filter space. 

      ![Roles template add condition drag attribute](assets/roles-template-role-attribute.png){width="700" zoomable="yes"}

      >[!NOTE]
      >
      >If you have custom person fields defined in the account audience schema in Experience Platform, these fields are also available to use as person attributes in conditions.

   * Use the attribute to create a matching filter using one or more values. 
    
      In the following example, the Job title attribute is used to identify a match for Decision Maker. Any value for title that starts with `Director` or `Sr Director` evaluates as true for the condition.

      ![Roles template condition example using job title](assets/roles-template-condition-example-job-title.png){width="700" zoomable="yes"}

   * If needed, add another attribute and condition that further refines the criteria for a match to the role.

   * Click **[!UICONTROL Done]**.

1. For each additional role that you want to include for the template, click **[!UICONTROL Add another role]** and repeat steps 1 and 2 to define the role.

   ![Roles template with multiple roles defined](assets/roles-template-multiple-roles.png){width="700" zoomable="yes"}

>[!BEGINSHADEBOX "Marketo Engage list membership"]

In Marketo Engage, _Smart Campaigns_ check membership of programs to ensure that leads don't receive duplicate emails and aren't members of multiple streams of emails at the same time. In Journey Optimizer B2B, you can check for Marketo Engage list membership as a condition for your roles template to help eliminate duplication in buying group membership and journey activities.
   
To use list membership as a role condition, expand **[!UICONTROL Special Filters]** and drag the **[!UICONTROL Member of List]** condition into the filter space. Then complete the filter definition to evaluate membership in one or more Marketo Engage lists.

![Roles template condition for Marketo Engage list membership](assets/roles-template-conditions-member-of-list.png){width="700" zoomable="yes"}

>[!ENDSHADEBOX] 

Your changes are auto-saved in the _Draft_ status. If you are not ready to publish the roles template, click the left (back) arrow at the top of the page and return to the _[!UICONTROL Roles templates]_ list.

### Publish the roles template

If the template is ready for use, click **[!UICONTROL Publish]** at the top-right.

Publishing the template sets the status to _Live_ status and makes it available for association with a solution interest. There must be at least one defined role to publish the roles template. 

## Edit a draft roles template

When a roles template is in a _Draft_ state, you can continue to edit the defined roles. Any changes that you make are automatically saved.

Change any of the settings in the header of the role card, including the buying group role, weighting, auto-assignment, and completeness scoring requirement.

![Change buying group role properties](./assets/roles-template-role-properties.png){width="600"}

### Modify the conditions for a role

To change the condition/filtering logic for any of the roles, click the _Edit_ ( ![Edit icon](../assets/do-not-localize/icon-edit.svg) ) icon at top right of the role card. This action opens the _[!UICONTROL Conditions]_ workspace where you can modify an existing filter, add or remove a filter, or change the filter logic.

### Delete a role card

If you want to remove a role from the template, click the _Delete_ ( ![Delete icon](../assets/do-not-localize/icon-delete.svg) ) icon in the role card. 

### Set the priority for roles

You can re-order the roles within the template, which determines the priority for assigning leads to a role. There is a **[!UICONTROL Priority]** controller displayed to the right of each role card. Click the _Up_ or _Down_ arrow at the right to move the role card up or down in priority.

![Change role priority](./assets/roles-template-role-priority.png){width="700"}

## Delete a roles template

You can delete a roles template if it is in the _Draft_ status. 

1. Select the roles template from the list to open it. 

1. Click **[!UICONTROL Delete]** at the top right.

   ![Change role priority](./assets/roles-template-delete.png){width="700"}

1. In the dialog, click **[!UICONTROL Delete]** to confirm.

## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3433079/?learn=on)
