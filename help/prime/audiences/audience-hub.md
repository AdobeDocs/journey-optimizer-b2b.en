---
title: Audiences
description: Placeholder page for audiences.
---
# Audiences

Audience Hub

* People Lists
   * Dynamic
   * Static
* Buying Groups
* Account Lists

## Audience Hub

The AI Audience Hub is a centralized, AI-driven starting point for all audience-related capabilities across AJO B2B. It is designed to accelerate first-time user success while progressively unlocking advanced intelligence, insights, and control for returning and power users.

The Hub acts as:

* A guided starting point for discovering, creating, and refining person lists, account lists, and buying groups

* A visibility layer for audience health, coverage, overlap, engagement patterns, and AI-driven insights

* A control center for audience governance, optimization, reuse, and readiness for activation across journeys and sales workflows

### High level structure

Prompt-based starting point - Quick Start prompts and freeform input to help users discover, create, or optimize audiences.

1. AI insights feed - Surfaces key audience signals such as overlap, gaps, saturation risk, and optimization opportunities.

1. Adaptive audience library - A personalized view of people lists, account lists, and buying groups that adapts based on usage, relevance, and activation.

1. Optimization and arbitration nudges - Guides users to refine, split, or reuse audiences before activation.

1. Audience visibility and reporting - High-level insight into audience health, engagement patterns, and usage across active journeys.


### Empty and Error States (High-Level)

No audiences / no data - Show Quick Start prompts to help first-time users create or import person lists

Low data or incomplete audience - Explain what's missing (e.g., insufficient contacts, missing persona coverage, or low engagement data) and suggest next steps.

AI insights unavailable - Provide a graceful fallback with a clear explanation, so users understand why insights aren't shown and what actions they can take manually.

## People Lists

Static people lists are simply a list of names from the database. A single person in the database can be a member in many different static lists. You can use these lists for:

* A pre-selected list to receive a marketing message.
* A _competitors_ list that you use to send mischievous counter-intelligence messages.
* A temporary list of people in a particular state, who are then removed from a journey when they exit that state.

Dynamic lists allow you to find specific groups of people using simple filters. A single person in the database can be a member in many different dynamic lists. You can use these lists for:

?? Examples of dynamic list usage

The primary difference between a static and dynamic lists:

Type    Logic
Dynamic   Based on defined rules
Static    Based on explicitly adding/removing each person

Audience management is where you will build and manage audiences in Adobe Journey Optimizer B2B Edition Prime.


Click People lists in the left navigation to view the people lists in your instance. Use the tabs on the top of the page to switch between viewing the inventory of dynamic and static lists.



From this page you can:

Create new Dynamic and Static lists
Search for existing lists
See asset information
Access lists to see their membership


Creating an audience


To create a new Dynamic or Static list:

Click the "Create list" button at the top right of the People lists page
Give your list a name, description (optional) and choose which type of audience list you want to create:
Static - people are added by qualifying for filters. The list membership will not update unless you manually qualify or disqualify records.
Dynamic: people are added by qualifying for filters. The list membership will refresh automatically, updating membership dynamically
Click Create to create the list.


Note: Lists cannot be deleted or duplicated at this time.



Static Lists
Membership of Static lists is defined by simple filters referencing people attributes and activities. Membership of the Static list is does not change until a user qualifies or disqualifies members manually.

To add members to a Static list:
In a Static list, click the Add people at the top right to open the rules modal.
Define the rules for qualifying your leads by dragging and dropping filters from the left. Audiences can be filtered by any combination of:
Activity history
Company attributes
Person attributes
Special filters such as Journey membership
Click Done to save your changes
Click the Members tab. After a brief time, qualifying members will appear.


To remove members of a Static list:
In a Static list, click the Remove people at the top right to open the rules modal.
Define the rules for qualifying your leads by dragging and dropping filters from the left.
Click Done to save your changes
Click the Members tab. After a brief time, qualifying members will be removed.


Dynamic Lists
Membership of Dynamic lists is defined by simple filters referencing people attributes and activities. Membership of the Dynamic list is automatically maintained by qualifying and disqualifying leads according to the filter logic.



To define Dynamic list logic:
In a Dynamic list, click the Rules tab at the top of the page.
Click the Edit rules button to open the rules modal
Define the rules for qualifying your leads by dragging and dropping filters from the left. Audiences can be filtered by any combination of:
Activity history
Company attributes
Person attributes
Special filters such as Journey membership
Click Done to save your changes
Click the Members tab. After a brief time, qualifying members will appear.
Clicking the name of a person in the list will open their detail page where you can look at their summary and recent activities.


