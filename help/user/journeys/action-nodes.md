---
title: Take an Action
description: Learn about the Take an action node type that you can use for orchestrating your account journeys in Journey Optimizer B2B Edition.
feature: Account Journeys
---
# Take an action

In your account journey, you can add a _Take an action_ node to execute an action, such as send an email, change a score, assign to a buying group, and so on. Actions are typically what you want to happen as a result of some kind of trigger, such as an event or a previous action. 

## Account actions

Use an action on accounts when you want to apply a change to all people that are part of accounts on the node path.

### Actions and constraints {#account-action-constraints}

| Action | Constraints |
| ------ | ----------- |
| Account Change Data Value | Select attribute<br/>New value |
| Account Interesting Moment | Type (Email, Milestone, or Web)<br/>Description (optional)|
| Add Account to (other) Journey | Select live Account Journey |
| Add to account list | Select a live static account list |
| Remove Account from Journey | Select live Account Journey |
| Remove from account list | Select a live static account list |
| Send Sales Alert | Select solution interest<br/>Send email to|
| Update Buying Group Stage | Select solution interest<br/>Select buying group stage |
| Update Buying Group Status | Select solution interest<br/>Status (required, 50 characters max) |

### Add an account-based action

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

   ![Add journey node - take an action](./assets/add-node-action.png){width="400"}

1. In the node properties on the right, choose **[!UICONTROL Accounts]** for the action.

1. Select an action from the list and set any values for the action.

   ![Journey node - take an action on an account](./assets/node-take-action-account.png){width="700" zoomable="yes"}

## People actions

Use an action on people when you want to apply a change to all people on the node path. This node type can be used within the split path by people or split path by accounts.

### Actions and constraints {#people-action-constraints}

| Action | Constraints |
| ------ | ----------- |
| Account Change Data Value | Select attribute<br/>New value |
| Account Interesting Moment | Type (Email, Milestone, or Web)<br/>Description (optional)|
| Add Account to (other) Journey | Select live Account Journey |
| Remove Account from Journey | Select live Account Journey |
| Send Sales Alert | Select solution interest<br/>Send email to|
| Update Buying Group Stage | Select solution interest<br/>Select buying group stage |
| Update Buying Group Status | Select solution interest<br/>Status (required, 50 characters max) |

### Add a people-based action

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

1. In the node properties on the right, choose **[!UICONTROL People]** for the action.

1. Select an action from the list and set any values for the action.

![Journey node - take an action on people](./assets/node-take-action-people.png){width="700" zoomable="yes"}
