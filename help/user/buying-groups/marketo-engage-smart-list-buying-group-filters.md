---
title: Buying Group Filters in Market Engage
description: Learn about using buying group membership for defining filters in Marketo Engage Smart Lists.
feature: Buying Groups
---
# Buying group filters in Market Engage

As a Marketer, you might want to suppress campaigns in Marketo Engage for people that are part of buying groups in Journey Optimizer B2B Edition. You can also inform the lead scoring workflows in Marketo Engage using information about the leads associated with buying groups. For example:

* Is this lead part of a buying group?
* Is the buying group complete and engaged?

If these conditions are true, you might choose to score lead the higher. If not, you might choose not to mark it as a marketing-qualified lead (MQL).

In your Marketo Engage instance that is connected to Journey Optimizer B2B Edition, you can use the _[!UICONTROL Member of Buying Group]_ filter in your Smart Lists to identify these leads according to your campaign strategy.

1. After you [create a Smart List in Marketo Engage](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-lists-and-static-lists/creating-a-smart-list/create-a-smart-list){target="_blank"}, select the **[!UICONTROL Smart List]** tab to open the filter editor. 

1. In the filters list on the right, scroll down the list and expand the **[!UICONTROL Special Filters]** folder.

1. Click the **[!UICONTROL Member of Buying Group]** filter and drag it onto the filter definition area.

   ![Add the Member of Buying Group filter to the Smart List](./assets/me-member-of-buying-group-filter-add.png){width="700" zoomable="yes"}

1. Set the _[!UICONTROL Member of Buying Group]_ option to **[!UICONTROL true]** or **[!UICONTROL false]**. 

   This constraint is required for the definition.

1. (Optional) Add other buying group-related constraints to the filter according to how you want to identify leads for the Smart List.

   * Click **[!UICONTROL Add Constraint]** at the top right of the filter card.

     ![Select another constraint](./assets/me-member-of-buying-group-filter-add-constraint.png){width="700" zoomable="yes"}

   * Select the constraint that you want to add, such as _Completeness Score_ or _Solution Interest_.

   * Set the evaluation that you want to use for a match. For a score, you can use an exact match, or a range that is above or below the number you enter. 
   
      For a discrete item, such as the solution interests defined in Journey Optimizer B2B Edition, you can select one or more items for the list.
      
      ![Select a value for the constraint from the list](./assets/me-member-of-buying-group-filter-constraint-list.png){width="600" zoomable="yes"}

      Select the first one and click the selector again to open the _[!UICONTROL Multiple Value Chooser]_ dialog.

      ![Select multiple values for the constraint](./assets/me-member-of-buying-group-filter-constraint-multiple-value.png){width="500" zoomable="yes"}

      Move any of the remaining items over to the right and click **[!UICONTROL OK]** when you have the list of items that you want to use for the constraint.

   * Repeat these actions to add as many of the constraints that you need.

   ![Member of Buying Group filter with multiple constraints](./assets/me-member-of-buying-group-filter-constraints-complete.png){width="600" zoomable="yes"}
