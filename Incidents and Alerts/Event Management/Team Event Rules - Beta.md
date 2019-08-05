---
title: "Team Event Rules - Beta"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "The following article references functionality that is not yet generally available. While it is being developed, you may see changes to the look, feel and features available. If you are interested in accessing this early beta functionality, please [contact PagerDuty Support](mailto:support@pagerduty.com)."
}
[/block]
Team event rules, similar to [global event rules](https://support.pagerduty.com/docs/global-event-routing), allow you to build out rulesets on a team level. These rules perform actions on events and dictate how they turn into incidents on a service. Team event rules and service event rules are designed to work together. In any particular ruleset, you can define routing behavior to services that you have permission to edit (see Required User Permissions note, below). You can create and manage multiple sets of rules per team with a distinct integration endpoint per set. All events that are sent to a team ruleset integration endpoint are filtered through that team’s specific set of rules. Any successfully processed event sent to an integration endpoint that does not match any of the defined rules will be suppressed by default using the ‘catch-all’ rule and will not be routed to a service. This default behavior can be adjusted per ruleset.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c4e53c9-team-event-rules-main-screen.png",
        "team-event-rules-main-screen.png",
        1132,
        700,
        "#f5f5f6"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "If your account has [advanced permissions](https://support.pagerduty.com/docs/advanced-permissions), you must have a Manager base role to create and edit team rulesets. For accounts without Advanced Permissions, you must have the [role](https://support.pagerduty.com/docs/user-roles) of User to edit a ruleset for your team."
}
[/block]
#Creating and Managing Team Rulesets

Ruleset requirements:

- A ruleset must have a unique name across the entire account.
- A ruleset should belong to a team. If a ruleset is not associated to a specific team, that ruleset is only manageable by a Global Admin.
- Only those who have a Manager role and permissions on that team can edit the rulesets of that team.

To create a ruleset:

1. Navigate to **Configuration** and select **Event Rules**. 
2. On the Event Rules screen, select **Team Rulesets** and click the green **Create Ruleset** button in the top right corner. 
3. You will be prompted to enter a **Name** for your ruleset as well as which **Team** you want associated with it. 
4. The next screen will display your **Integration Key**, as well as an **Email address** and **HTTP endpoint for API** that you can use for routing. You can refer back to this information when you are configuring an integration. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/13d4609-integration_key_tr_kb.png",
        "integration_key_tr_kb.png",
        3325,
        1456,
        "#f7f6f5"
      ]
    }
  ]
}
[/block]
5. On the same screen, you will automatically have a “Catch-All Rule” in the ruleset. You may edit this rule by clicking the :fa-cog: on the right hand side and selecting **Edit Rule**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/51f4761-edit_catch_all_tr.png",
        "edit_catch_all_tr.png",
        3325,
        1456,
        "#f7f7f7"
      ]
    }
  ]
}
[/block]
6. To add a new rule, click the green **New Event Rule** button. Enter your preferences in the **Which events should this rule apply to?** and **What actions should be performed on these events?** sections. Please read our [Team Event Rule Actions](https://support.pagerduty.com/docs/team-event-rules#section-team-event-rule-actions) section for more information on your options. Click **Save**. You may optionally add as many rules as you need.

To edit a ruleset:

1. Navigate to **Configuration** and select **Event Rules**. 
2. On the Event Rules screen, select **Team Rulesets** and click the **name** of the ruleset you wish to edit.
3. There are two editing options available:
    - If you need to edit the name of the ruleset or the team it belongs to, click **Edit Ruleset** on the upper right. 
    - If you would like to edit the rules themselves, click the :fa-cog: on the right hand side and select **Edit Rule**. 


#Team Event Rule Actions

* Route an alert to a particular service
* Tailor event actions as trigger / resolve
* Field extraction for the duplication key, summary or description
* [Change the severity](https://support.pagerduty.com/docs/dynamic-notifications) of the resulting alert
* [Suppress the alert](https://support.pagerduty.com/docs/event-management#section-suppression-and-event-rules) altogether 

Incident behavior adjustments are available with [Event Intelligence](https://support.pagerduty.com/docs/event-intelligence) only:
* Wait to create an incident until a given threshold of identical events occur within a set time limit
* Add contextual notes to an incident
* Change the priority of the incident
 
Team event ruless can be scheduled for a specific time or on a recurring schedule with the Event Intelligence package. API-based events with JSON/[PD-CEF](https://support.pagerduty.com/docs/pd-cef) fields ([Events v2 API](https://v2.developer.pagerduty.com/docs/events-api-v2) format) and email-based events are both supported for team rulesets. 

 

#FAQ
##What is the difference between team event rules and global event rules?

Event rules can either be applied globally or across a set of services to unique integration endpoints. We recommend implementing routing at either the global or team level.  Event rules at the global level are all applied to events sent to the one, unique global integration key. Event rules at a team level are applied to events sent to each distinct ruleset’s integration key. Events sent to these integration keys can be routed to services with the appropriate permissions.

##What is the difference between service event rules (currently in Beta) and team event rules?

PagerDuty event rules can be written and applied globally, across any set of services, or on individual services. Event rules can impact different scopes of control without interfering with each other.

Event rules for a service do not have a default catch-all rule. When an event arrives at a service, the mandatory fields that a catch-all rule would provide already exist via the service’s configuration. In contrast, event rules at the global or team level do have a catch-all rule. 
Events can be directed to a service through a global event rule, a team event rule, or a direct integration on the service. You do not need to set up a separate integration key to use event rules for a service. 

We recommend implementing rules at the smallest applicable scope. For example, if a particular service is going under maintenance, it is better to implement a suppression rule on that service than a team or global rule scoped to only that service. This results in fewer rules in the global ruleset, and more visibility for the service owners into actions affecting their alerts.


##Rule Type Use Cases

[block:parameters]
{
  "data": {
    "h-0": "Use Case",
    "h-1": "Rule Type",
    "h-2": "Implementation",
    "0-0": "The service an event should go to depends on specific information in the payload",
    "0-1": "Global Event Rules",
    "0-2": "If host.name is equal to CSE-1393 then route to Database Monitors",
    "1-0": "Incidents for a particular service are getting grouped improperly",
    "1-1": "Service Event Rules",
    "1-2": "Extract one field into dedup_key",
    "2-0": "You have a team responsible for several services. Each service integrates with a monitoring system consisting of many nodes, but there are only some nodes whose status the team needs to be apprised of.",
    "2-1": "Team Event Rules",
    "2-2": "Use the team ruleset endpoint to integrate with the monitoring service, and set up a condition which names the specific nodes you would like to monitor. The rest will be suppressed by default."
  },
  "cols": 3,
  "rows": 3
}
[/block]