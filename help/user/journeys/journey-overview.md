---
title: Account journeys
description: Learn about account journeys and how you can create and manage them.
exl-id: 5c22f11f-1967-4b55-8aee-16371173c040
---

# Account journeys

Define sales-driven engagement that includes email, SMS, and more inside account journeys to coordinate inbound marketing with outbound sales activities for each buying group member.

## Access and browse Account Journeys

1. In your Adobe Experience Platform home page, click Adobe Journey Optimizer B2B Edition.

1. On the left navigation, click **[!UICONTROL Account journeys]**.

   ![Access account journeys](./assets/account-journey-browse.png){width="800" zoomable="yes"}

   The displayed journeys page includes the following columns:

   * [!UICONTROL Name] (click the name to open the account journey for editing)
   * [!UICONTROL Status]
   * [!UICONTROL Description] 
   * [!UICONTROL Created by]
   * [!UICONTROL Last updated at]
   * [!UICONTROL Last updated by]
   * [!UICONTROL Published on]
   * [!UICONTROL Published by]

  This table includes the ability to search by Name and Created by. Sort is currently unavailable.

You can customize the displayed table by clicking the columns icon in the top right corner and selecting or clearing the checkboxes. 

![Choose the columns to display in the acount journeys list](./assets/account-journeys-list-columns.png){width="800" zoomable="yes"}

## Create an account journey

1. Click **[!UICONTROL Create Account Journey]** at the top-right corner of the page. 

1. In the dialog, enter a name (required) and description (optional) for the account journey.

1. Click **[!UICONTROL Create]**.

## Anatomy of an account journey

Click the name (displayed as a link) in the _[!UICONTROL Account journeys]_ list to review the details, make changes, and take actions.

![Account journey workspace](./assets/account-journeys-list-columns.png){width="800" zoomable="yes"}

The editor header of each journey includes: 

* Journey name
* Ability to edit the name (Edit icon)
* Status of the Journey

The following actions are available in the header:

* **Publish** - You can publish a journey if there are no blocker errors. When published, a Journey status changes to _Live_. If the journey has errors, the button is dimmed with content information: `Resolve errors before publishing`.
* **Duplicate** - This action is similar to a clone function, but the duplicated journey does not include any assets.
* **Close to new entries** - If you close a journey, accounts currently in the journey continue their path in the journey and no further journey entrance can happen. A closed journey cannot be restarted. You can duplicate a closed journey.
* **Abort** - If you stop a journey, accounts in the journey immediately stop their progress and no further journey entrance can happen. A stopped journey cannot be restarted. If you block new entrances without stopping people's progress, consider closing the journey instead.
* **Delete** - This action permanently deletes the journey.

The status of a Journey changes based on the actions you take. Based on status of a journey, certain actions are/are not available in the header.

* _Draft_ - An unpublished Journey that is editable. Available actions:
   * Publish
   * Duplicate 
   * Delete 
* _Live_ - Journey status changes from Draft to Live once a journey is published. In this state, it is longer editable. Available actions:
   * Duplicate 
   * Close to new entries 
   * Abort 
* _Closed to new entries_ -  Journey status changes from Live to Closed to new entries when user clicks on Close to new entries in the top nav. Available actions:
   * Duplicate
   * Abort 
* _Aborted_ - Journey status changes from Live or Closed to new entries when you abort a journey. An aborted a journey cannot be restarted. Available actions:
   * Duplicate
   * Delete
* _Finished_ - When all accounts in a journey complete the. journey, the status changes from Live or Closed to new entries to Finished. Available actions:
   * Duplicate
   * Delete

## Get started with a journey

1. On the left navigation, click **[!UICONTROL Account journeys]**.

1. Click **[!UICONTROL Create Account Journey]** at the top-right of the page.

1. In the dialog, enter a unique **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional).

   ![Create Account Journey dialog](./assets/account-journey-create-dialog.png){width="400"}

1. Click **[!UICONTROL Create]**.

### Add the account audience for your journey

An account journey always starts with Account Audience where you can add input to your journey.
   
1. Click **[!UICONTROL Account audience]** node to display the node properties on the right.

   ![Account audience node](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Add account audience]**.

You can select an audience segment that was previously selected by clicking on add audiences button.

1. To create a new audience segment, select **[!UICONTROL Account audiences]** in the left navigation.

1. Click **[!UICONTROL Create audience]** and follow the steps described in the [Segmentation Service guide](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/account-audiences.html#create){target="_blank"}.

### Building blocks of a journey

You can build your journey using the following nodes

* **_Listen for an event_** - Move your audience forward to the next step in the journey when an event occurs
  * You can also define the amount of time the Journey will wait for this event. Journey will end after timeout.
  * Additionally, you can choose to add other nodes on your timeout path
* **_Take an action_** - Execute an action like send an email, change score, etc..
* **_Split paths_** - Split your audience based on filter conditions
* **_Wait_** - Wait for a certain duration before moving to the next step
* **_Merge_** - Different paths in your journey can be merged using this node

Each of these nodes can be applied on the people or account level:

* **Action on accounts**: Action will be applied to all people that are part of accounts on this path
* **Action on people**: Action will be applied to all people on this path. Action on people can be used within split path by people or split path by accounts
* **Listen to events on accounts**: If at least one person from an account triggers an event the account moves forward to next step on the journey
* **Listen to events on people**: Events on people can only be applied on account path, it is not available with split by people node    
* **Split Path by account**: Paths split by accounts can include both account and people actions and events, and these paths can be split further.
  _How does split path by accounts node work?_ - When a user adds split path node and chooses Account, each path that is added includes an end node with ability to add nodes to each edge.
  It is possible to split path by Accounts repeatedly, such as in a nested manner.
  A split path includes an option for not adding default path. Accounts/people who do not qualify do not move forward in the journey.
  These paths can be combined using a merge node
  We can support a maximum of 25 paths
* **Split Path by people**: Paths split by people and can include only people actions, and these paths can't be split again. Paths automatically join back.
  _How does split path by people node work?_ - Split path by people are grouped nodes; they automatically merge so all the people in the audience can move forward to the next step without losing context of the accounts they belong to.
  Split path for people cannot be nested I.e you cannot add split path for people on a path that is in this grouped node
  Split path will include option of not adding default path. Accounts/people who do not qualify do not move forward in the Journey
  It can support a maximum of 25 paths.

<  Note to tech writer: Please include a couple of screenshots for this section from the following link based on what you think would work well. >

To help you build a journey without running into errors, the following guard rails are in place:

* Deleting Split path nodes: You cannot delete this node without deleting all subsequent nodes in each path.
* Deleting Merge node: It can be deleted only when there is one path connected to it. To delete merge node, leave only one path selected.
* Switching between account and people: You cannot change selection from accounts to people without deleting all subsequent nodes in each path.

### Use split path by account node

1. Start by navigating to a journey.
1. Click the plus icon on a path and add split path node
1. In the property rail, select account radio button
1. To define condition applicable to a path, click apply condition.
1. In the conditions modal, drag and drop filters from the left nav to add filters.
1. Fine tune your conditions by applying filter logic in the top navigation.
1. Click done
1. To add more paths, click add path and repeat the previous steps to add conditions applicable to this path.
1. You can also label each path based on these conditions or use pre-populated default labels.
1. Lastly, you can add a default path for accounts not qualified for the other paths. If not, the journey ends for these accounts.


### Use split path by people node

1. Start by navigating to a journey
1. Click the plus icon on a path and add split path node
1. In the property rail, select people radio button
1. To define condition applicable to a path, click on apply condition 
1. In the conditions modal, drag and drop filters from the left nav to add filters
1. Fine tune your conditions by applying filter logic in the top nav of the modal
1. Click done
1. To add more paths, click add path and follow the steps listed above to add conditions applicable to this path
1. You can also label each path based on these conditions or use pre-populated default labels
1. Lastly, you can add a default path for people not qualified for the above paths. If not, Journey will end for these people
1. Now that you have conditions defining each path that you're splitting your audience on people level, you can add actions that you want to take on people.

>[!NOTE]
>
>When you split audience by people, you can only add people actions.


### Add people actions

1. Start by navigating to a journey
1. Click on the plus icon on the path and add select Take an action
1. In the property rail, under "Action on", choose accounts radio button
1. Select action from the drop down

### Add people events

1. Start by navigating to a journey
1. Click on the plus icon on the path and add select Listen from an event
1. In the property rail, under "Event type", choose accounts radio button
1. Select event from the drop down
1. Click on edit event where you can define details for your event

### Add account actions

1. Start by navigating to a journey
1. Click on the plus icon on the path and add select Take an action
1. In the property rail, under "Action on", choose accounts radio button
1. Select action from the drop down

### Add account events

1. Start by navigating to a journey
1. Click on the plus icon on the path and add select Listen from an event
1. In the property rail, under "Event type", choose accounts radio button
1. Select event from the drop down
1. Click on edit event where you can define details for your event

### Add timeout to people and account level events

1. Start by navigating to a journey
1. Click any listen for event node to open property rail
1. Enable timeout toggle o define the amount of time the Journey will wait for this event. Journey will end after timeout.
1. You can select the duration for which the journey will wait for an event to occur before it times out
1. You can choose to end the path here or take a different course of action by enable "set time out path"
1. Enable "Set timeout path" check box, this will create a new path in your journey where you can add actions and events applicable to accounts when a certain event does not occur

### Merge or unmerge paths

1. Navigate to a Journey and click the plus icon on a path.
1. Add split path by account node.
1. Click the node to open its properties on the right.
1. Click Add path to create three paths.
1. Add a combination of actions and events to each path.
1. Click the plus icon for any one of these paths and choose merge from the displayed options.
1. In the merge node properties, select the paths you want to merge.
   You should now see that the paths have merged so accounts from several different paths have merged to a single path and can continue to progress through the journey
1. Similarly, you can unmerge paths by navigating back to the property rail of a merge node and unchecking certian paths

### Add and delete a node

1. Navigate to a Journey
1. Click on the plus icon on the path and add select Take an action
1. In the property rail, under "Action on", choose accounts radio button
1. Select action from the drop down
1. Now click on delete icon, confirm that you want to delete the node

## Add and delete a path

1. Navigate to a Journey
1. Click on plus icon on a path and add split path node
1. In the property rail, select account radio button
1. To add more paths, click on add path 
1. With each path that is created in the journey, you will notice a new path card has been added in the property rail
1. Navigate to one of the paths in the journey and add action or event nodes to this path using the plus icon
1. Now navigate back to split path node and open the property rail
1. You will notice that paths that have nodes on them cannot to be deleted
1. In order to delete these paths, you will have to delete all the nodes on that path first

## Schedule a journey

1. You can schedule your journey by clicking [!UICONTROL Journey settings] in the header.
1. Your journey can start immediately or on a specified future date.
1. The end date of a journey can be a maximum of three years from start date (this field is mandatory).
1. When you are ready to publish your journey, you can review these settings when you click [!UICONTROL Publish].
1. After a journey is published (_Live_ status), you can update the end date of the journey but not the start date

