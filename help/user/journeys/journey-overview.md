---
title: Account Journeys
description: Learn about...
exl-id: 5c22f11f-1967-4b55-8aee-16371173c040
---
# Account Journeys

< PM - What is an account journey and why should I be interested?  How does it relate to the other product components? What can I accomplish if I continue to read and learn about this fetaure? >



## Access and browse Account Journeys

1. In your Adobe Experience Platform home page, click Adobe Journey Optimizer B2B Edition.

1. On the left navigation, click **[!UICONTROL Account Journeys]**.

   The displayed journeys page includes the following columns:

   * Name (hyperlinked)
   * Status
   * Description 
   * Created by
   * Last updated at
   * Last updated by
   * Published on
   * Published by

  This table includes the ability to search by Name and Created by only (i.e exact match). Sort is currently unavailable.

You can customize the table using the filter option in the top right corner.

## Create an Account Journey

1. Click **[!UICONTROL Create Account Journey]** at the top-right corner of the page. 

1. In the dialog, enter a name (required) and description (optional) for the account journey.

1. Click **[!UICONTROL Create]**.

## Anatomy of an Account Journey

The editor header of each journey includes: 

* Journey name
* Ability to edit name via edit modal which can be access via edit icon
* Status of the Journey (more details below)

The following actions are available in the header:

* Publish - users can publish Journeys if there are no blocker errors, once published a Journey status changes to live. If Journey has errors this button with be grayed out with hover over context "Resolve errors before publishing
* Duplicate - this is similar to clone functionality, duplicated Journey will not include any assets
* Close to new entries - If you close a journey, accounts currently in the journey will continue their path in the journey and no further journey entrance will happen. A closed journey cannot be restarted. You can duplicate a closed journey.
* Abort - If you stop a journey, accounts in the journey will immediately stop their progress and no further journey entrance will happen. A stopped journey cannot be restarted. If you don't want to stop people's progress but only block new entrances, consider closing the journey instead.
* Delete - this action will permanently delete the journey

The status of a Journey will change based on the top nav actions you take:

* Draft - unpublished Journey that is editable
* Live - Journey status changes from Draft to Live once a journey is published. Its not longer editable
* Closed to new entries -  Journey status changes from Live to Closed to new entries when user clicks on Close to new entries in the top nav.
* Aborted - Journey status changes from Live or Closed to new entries when user aborts a journey. Once aborted a journey cannot be restarted
* Finished - When all accounts in a journey complete the. journey, the status changes from Live or Closed to new entries to Finished.

Based on status of a journey, certain actions are/are not available in the editor header:

* Status = Draft
  * Publish (Primary CTA)
  * Duplicate 
  * Delete 
* Status = Live
  * Duplicate 
  * Close to new entries 
  * Abort 
* Status = Closed to new entries
  * Duplicate (Primary CTA)
  * Abort 
* Status = Aborted
  * Duplicate (Primary CTA)
  * Delete
* Status = Finished
  * Duplicate (Primary CTA)
  * Delete

## Get started with a Journey


### Input the account audience for your journey

1. Click Account Journeys tab on the left nav
2. Click journey from the inventory table to navigate to a journey
3. Journey always starts with Account Audience where you can add input to your Journey. Click Account audience node to open the property rail
4. Click Add account audience, this opens the add audience modal
5. You can select an audience segment that was previously selected by clicking on add audiences button.
6. To create a new audience segment, navigate to Account audiences tab on the left nav.
7. Click create audience and follow steps mentioned at https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/account-audiences.html?lang=en#create

### Building blocks of a Journey

You can build your journey using the following nodes

* Listen for an event - Move your audience forward to the next step in the journey when an event occurs
  * You can also define the amount of time the Journey will wait for this event. Journey will end after timeout.
  * Additionally, you can choose to add other nodes on your timeout path
* Take an action - Execute an action like send an email, change score, etc..
* Split paths - Split your audience based on filter conditions
* Wait - Wait for a certain duration before moving to the next step
* Merge - Different paths in your journey can be merged using this node

Each of these nodes can be on people or account level:

* Action on accounts: Action will be applied to all people that are part of accounts on this path
* Action on people: Action will be applied to all people on this path. Action on people can be used within split path by people or split path by accounts
* Listen to events on accounts: If at least one person from an account triggers an event the account moves forward to next step on the journey
* Listen to events on people: Events on people can only be applied on account path, it is not available with split by people node    
* Split Path by account: Paths split by accounts can include both account and people actions and events, and these paths can be split further.
  How does split path by accounts node work?
  When a user adds split path node and chooses Account, each path that is added will include an end node with ability to add nodes to each edge
  It is possible to split path by Accounts repeatedly i.e in a nested manner
  Split path will include option of not adding default path. Accounts/people who do not qualify do not move forward in the Journey
  These paths can be combined using merge node
  We can support a maximum of 25 paths
* Split Path by people: Paths split by people can include only people actions, and these paths can't be split again. Paths will automatically join back.
  How does split path by people node work?
  Split path by people are grouped nodes i.e they automatically merge so all the people in the audience can move forward to the next step without losing context of the accounts they belong to
  Split path for people cannot be nested I.e you cannot add split path for people on a path that is in this grouped node
  Split path will include option of not adding default path. Accounts/people who do not qualify do not move forward in the Journey
  We can support a maximum of 25 paths
 

<  Note to tech writer: Please include a couple of screenshots for this section from the following link based on what you think would work well. >

In order to help you build a journey without running into errors, we have the following guard rails in place

Deleting Split path nodes: You cannot delete this node without deleting all subsequent nodes in each path.
Deleting Merge node: It can be deleted only when there is one path connected to it. To delete merge node, leave only one path selected.
Switching between account and people: You cannot change selection from accounts to people without deleting all subsequent nodes in each path.

### Use split path by account node in a journey

1. Start by navigating to a journey
2. Click the plus icon on a path and add split path node
3. In the property rail, select account radio button
4. To define condition applicable to a path, click on apply condition 
5. In the conditions modal, drag and drop filters from the left nav to add filters
6. Fine tune your conditions by applying filter logic in the top nav of the modal
7. Click done
8. To add more paths, click on add path and follow the steps listed above to add conditions applicable to this path
9. You can also label each path based on these conditions or use pre-populated default labels
10. Lastly, you can add a default path for accounts not qualified for the above paths. If not, Journey will end for these accounts


### Use split path by people node:

1. Start by navigating to a journey
2. Click the plus icon on a path and add split path node
3. In the property rail, select people radio button
4. To define condition applicable to a path, click on apply condition 
5. In the conditions modal, drag and drop filters from the left nav to add filters
6. Fine tune your conditions by applying filter logic in the top nav of the modal
7. Click done
8. To add more paths, click add path and follow the steps listed above to add conditions applicable to this path
9. You can also label each path based on these conditions or use pre-populated default labels
10. Lastly, you can add a default path for people not qualified for the above paths. If not, Journey will end for these people
11. Now that you have conditions defining each path that you're splitting your audience on people level, you can add actions that you want to take on people.

>[!NOTE]
>
>When you split audience by people, you can only add people actions.


## Add people actions to your Journey

1. Start by navigating to a journey
2. Click on the plus icon on the path and add select Take an action
3. In the property rail, under "Action on", choose accounts radio button
4. Select action from the drop down

### Add people events to your Journey

1. Start by navigating to a journey
2. Click on the plus icon on the path and add select Listen from an event
3. In the property rail, under "Event type", choose accounts radio button
4. Select event from the drop down
5. Click on edit event where you can define details for your event

### Add account actions to your Journey

1. Start by navigating to a journey
2. Click on the plus icon on the path and add select Take an action
3. In the property rail, under "Action on", choose accounts radio button
4. Select action from the drop down

### Add account events to your Journey

1. Start by navigating to a journey
2. Click on the plus icon on the path and add select Listen from an event
3. In the property rail, under "Event type", choose accounts radio button
4. Select event from the drop down
5. Click on edit event where you can define details for your event

### Add timeout to people and account level events

1. Start by navigating to a journey
2. Click any listen for event node to open property rail
3. Enable timeout toggle o define the amount of time the Journey will wait for this event. Journey will end after timeout.
4. You can select the duration for which the journey will wait for an event to occur before it times out
5. You can choose to end the path here or take a different course of action by enable "set time out path"
6. Enable "Set timeout path" check box, this will create a new path in your journey where you can add actions and events applicable to accounts when a certain event does not occur

### Merge/Unmerge paths

1. Navigate to a Journey and click on plus icon on a path
2. Add split path by account node
3. Click on the node to open property rail
4. Click on add path button to create 3 paths
5. Add a combination of actions and events to each path
6. Now click on plus icon on any one of these paths, choose merge from the sub menu option
7. In the merge node property rail, select/unselect the paths you want to merge
8. You should now see that the paths have merged so accounts from several different paths have merged to a single path and can continue to progress through the journey
9. Similarly, you can unmerge paths by navigating back to the property rail of a merge node and unchecking certian paths

## Add and Delete a node

1. Navigate to a Journey
2. Click on the plus icon on the path and add select Take an action
3. In the property rail, under "Action on", choose accounts radio button
4. Select action from the drop down
5. Now click on delete icon, confirm that you want to delete the node

## Add and Delete a path

1. Navigate to a Journey
2. Click on plus icon on a path and add split path node
3. In the property rail, select account radio button
4. To add more paths, click on add path 
5. With each path that is created in the journey, you will notice a new path card has been added in the property rail
6. Navigate to one of the paths in the journey and add action or event nodes to this path using the plus icon
7. Now navigate back to split path node and open the property rail
8. You will notice that paths that have nodes on them cannot to be deleted
9. In order to delete these paths, you will have to delete all the nodes on that path first

## Schedule a Journey

1. You can schedule your journey by clicking on Journey settings button in the header
2. Your journey can start immediately or on a certain date in the future
3. The end date of a journey can be a maximum of 3 years from start date, this field is mandatory
4. When you are ready to publish your journey, you can review these settings when you click on the publish button 
5. When a journey is published i.e live, you can update the end date of the journey but not the start date
