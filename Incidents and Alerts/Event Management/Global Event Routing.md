---
title: "Global Event Routing"
excerpt: ""
---
[block:api-header]
{
  "title": "What Is Event Routing?"
}
[/block]
Routing enables you to send events to a single endpoint and write rules to define which team receives alerts based on content in those events.

API-based events with JSON/[PD-CEF fields](doc:pd-cef) and email-based events are both supported.
[block:api-header]
{
  "title": "Accessing, Creating, and Formatting Event Rules"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Access to create global event rules are granted to the account owner. With [advanced permissions](https://support.pagerduty.com/docs/advanced-permissions#section-getting-started-with-advanced-permissions), global admins will also have access to view event rules.\nTo enable all users with view-only access to event rules, please contact [PagerDuty Support](support@pagerduty.com)."
}
[/block]
Click on the **Configuration** menu at the top of the page on your PagerDuty account and choose **Event Rules**. Once on that page, click **New Event Rule**. You will be asked to fill in two sections: *conditions* and *actions*. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3a9d097-Global-Event-Routing-Recurring.png",
        "Global-Event-Routing-Recurring.png",
        2821,
        1286,
        "#fbfbfb"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
A *condition* indicates what you would like Event Routing to search for in inbound events. The corresponding *action* indicates what you would like Routing to do with an event that contains the selected *condition*.

You can either configure these in the UI, or use the [Global Event Rules API](https://v2.developer.pagerduty.com/v2/docs/global-event-rules-api).

##Supported Fields for Writing Rules

###Events Sent Through the API
You can use the JSON field names directly, i.e. `description`. For nested fields, separate names with a dot (.), i.e. `payload.summary`.

If you are sending data through additional fields, enter them exactly as they are sent to PagerDuty. For example, if your events have a `tags` field, enter that field name in your rule *condition* as `tags`.

###Events Sent Through Email
Rules may be based on the content of an email by entering the appropriate email field as the event field. The most common email fields are:

- `headers.from.0.address` (the from address)
- `headers.subject` (the subject line)
- `body` (the email body)

If your monitoring tool sends emails with **custom headers**, you can create rules based on those headers by including the prefix headers in front of the email header name when you enter that field name in your rule *condition*.

###Field Selector
You can view and choose relevant fields from your most recent event by using our JSON field selector:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0b454b9-image2.png",
        "image2.png",
        3770,
        1392,
        "#d1d3d5"
      ]
    }
  ]
}
[/block]
The JSON field selector will appear when you select **View a recent API event...** in the dropdown that appears when you click **Enter field name** while writing your rules.

##Field Extraction

Field extraction allows you to copy important data from one event field to another. Some fields can be used by PagerDuty for automation.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/21e7ad3-field_extraction.png",
        "field_extraction.png",
        1426,
        782,
        "#f8f8f8"
      ]
    }
  ]
}
[/block]
The `description` field is used to create the incident title. Titles should be descriptive and tell responders what is happening.

The `dedup_key` field is used to merge events into a single alert. Events with the same dedup_key can update the status of the alert they are automatically merged into.

Extraction rules must use valid [RE2 regular expression syntax](https://github.com/google/re2/wiki/Syntax).

##Formatting Rules

###What Operations Are Supported?
- A field contains/does not contain a value.
- A field equals/does not equal a value.
- A field exists/does not exist.
- A field matches/does not match a regular expression. Regular expressions must use [RE2 syntax](https://github.com/google/re2/wiki/Syntax ). Note that unlike service-level event rules, global rules only support one (e.g. the first) capture group within the regex.
[block:callout]
{
  "type": "info",
  "title": "",
  "body": "If you are new to regex, we suggest testing your rules with an online regex tester. [regex101](https://regex101.com/) and [rubular](http://rubular.com/r/G0ViTWxgFO) are both excellent tools."
}
[/block]
### How Do I Use Negative Operations?
Rules with negative operations, such as “does not contain” or “does not equal”, will match events when the field in question does not exist. As an example:

> - severity field does not equal `critical`

These rules will also match any events where the severity field does not exist. If you'd like to avoid this, you must add an additional condition that matches only when the field exists. For example:

When all conditions are true:
> - severity field exists
> - severity field does not equal `critical`

Note that you must select that all conditions must be true for the rule to match.

###What Actions Are Supported?
[block:parameters]
{
  "data": {
    "h-0": "Action",
    "0-1": "Send events to a service and follow the settings on that service for creating incidents and sending notifications to responders. For more information on defining how notifications will be sent to responders, see [service urgencies.](doc:dynamic-notifications)",
    "0-0": "Route to a service",
    "1-0": "Route to a service and suppress",
    "1-1": "No incident is created, no notifications are sent. Events can still be routed to a service, meaning they have the associated service name listed in the Alerts table.",
    "2-0": "Set severity",
    "2-1": "For events that do not have a [severity level](doc:pd-cef#section-pd-cef-fields) (such as emails), users can define one, or a new severity level can be set. \n\nSeverity can be used for [Dynamic Notifications](doc:dynamic-notifications), which are defined by the service settings. To use Dynamic Notifications, the events must be routed to a service that sets Dynamic Notifications based on severity levels.",
    "h-1": "Description",
    "3-0": "Do not route to a service",
    "3-1": "You may choose not to route events to a service. In this case, your events are [suppressed](doc:event-management#section-suppression) and will not be connected to a service. This is because the rules that determine incident settings (such as escalation policy assignment and notification settings) are associated with a service, and non-routed events do not have a service associated with them."
  },
  "cols": 2,
  "rows": 4
}
[/block]

[block:api-header]
{
  "title": "Where Do I Send Events to Use Routing?"
}
[/block]
The **Event Rules** page (**Configuration** <i class="fa fa-arrow-right" aria-hidden="true"></i> **Event Rules**) will display your routing integration key, as well as an endpoint and email address that you can use for routing. This integration key is case-sensitive.

You can use the [V1](https://v2.developer.pagerduty.com/docs/events-api) or [V2](https://v2.developer.pagerduty.com/docs/events-api-v2) events endpoint as well.

If using the [V1 events API](https://v2.developer.pagerduty.com/docs/events-api), use your routing integration key as your `service_key` value in your event JSON.

If using the [V2 events API](https://v2.developer.pagerduty.com/docs/events-api-v2), use your routing integration key as your `routing_key` value in your event JSON.
[block:api-header]
{
  "title": "Troubleshooting Event Routing:"
}
[/block]
###If None of Your Rules Are Working
This may be because you have not set up the integration key correctly in your monitoring tool. For event rules to work, you must use the integration key found to the right of your rules list under Integration Settings. If you are sending events through the Events API, use this integration key in the `service_key` field ([Events API V1](https://v2.developer.pagerduty.com/docs/events-api)) or the `routing_key` field ([Events API V2](https://v2.developer.pagerduty.com/docs/events-api-v2)).

###If One of Your Rules Is Not Working
This may be because you have not entered the field name correctly in the rule conditions. The field name is based on the data that is sent to PagerDuty, and *is not necessarily the same as the field name visible in the alert or incident in PagerDuty*. Refer to the data in your monitoring tool or integration for the correct field name.

For nested fields, format the field name with periods separating each level. For example, `field_group.sub_field.another_sub_field`.

If you have confirmed your field names are set up correctly, you may have a rule that is too broad that is ordered before the rule that is not working. Re-order your rules so that more specific rules are listed first. 

You may also want to check for rules with negative conditions ("does not contain" or "does not equal"), as these rules can match many events that do not contain the specified field. (See [How do I use negative operations?](#section-how-do-I-use-negative-operations?))

For nested fields, format the field name with periods separating each level of the object path. For example, `field_group.sub_field.another_sub_field`.
[block:callout]
{
  "type": "warning",
  "body": "If any object path specified in a condition rule is not present in the inbound event body (note, *paths are case sensitive*), the condition will not be met.\n\nFor instance, if one were add a condition to a rule that `payload.custom_details.long_description` must not contain the string `staging`, and the resulting event that comes in does not contain a property `payload.custom_details.long_description`, and all conditions must be true, then the rule will not apply because this particular condition would not be met and thus not all conditions would be met.",
  "title": "Default Condition Evaluation Behavior if the Object Path Does Not Exist"
}
[/block]

[block:api-header]
{
  "title": "Adding Notes With Event Rules"
}
[/block]
[Notes](https://support.pagerduty.com/docs/editing-incidents#section-add-a-note-to-an-incident) can be used to help responders resolve incidents quicker by including information or links related to the system that the event comes from.

Notes via Event Rules functionality is part of our [Event Intelligence](https://support.pagerduty.com/v1/docs/event-intelligence) product, which is purchased separately from the core PagerDuty platform.

Notes are added to incidents via the Global Event Rules Engine workflows. Users first set specific criteria in which notes information will be added. Users can then detail which information or links they want to include in the note. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc08207-image6.png",
        "image6.png",
        1052,
        244,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
If the event is added to an incident, notes can be seen on that incident's details page. Notes added by event rules will list the first account user as the author.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9a49464-image2.png",
        "image2.png",
        522,
        223,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Scheduled Event Rules"
}
[/block]
You can gain a greater degree of control over your event rules by detailing a single specific time in the future in which they will be active. This can be useful for testing rules and for planned maintenance. 

Scheduled Rules functionality is part of our [Event Intelligence](https://support.pagerduty.com/v1/docs/event-intelligence) product, which is purchased separately from the core PagerDuty platform.

Scheduled Rules are set within Global Event Rules Engine workflows. Users first set a single specific time window in which the rules they have created will apply. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ab27166-image3.png",
        "image3.png",
        2522,
        1624,
        "#f9fafa"
      ]
    }
  ]
}
[/block]
Users can then specify what actions are to be performed within this time window. For instance, users might want to suppress notifications.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b4c72fc-image4.png",
        "image4.png",
        1810,
        276,
        "#f8f8f8"
      ]
    }
  ]
}
[/block]
In this example, if alerts come into PagerDuty from host123, they will only be suppressed if they occur within the 5 minute window immediately following the creation of the rule. After 5 minutes, the rule will become inactive, and an alert from host123 will create an incident in PagerDuty. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/14785b8-image3.png",
        "image3.png",
        1483,
        422,
        "#f9f9f9"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Recurring Event Rules"
}
[/block]
If there are specific hours of the day or day(s) within a week when you would like an event to follow a particular rule, you can set its activity on an automatic, weekly recurring schedule. This feature is integration-specific and you can make additional changes, such as changing severity/priority, based on time of day. 

The Recurring Event Rules functionality is part of our [Event Intelligence](https://support.pagerduty.com/v1/docs/event-intelligence) product, which is purchased separately from the core PagerDuty platform.

To set a recurring schedule for an event rule, go to **Configuration** :fa-arrow-right: **Event Rules**, select the :fa-cog: dropdown next to the rule and then click **Edit Rule**. In the **When should this rule be active?** section, select **On a recurring schedule**, specify the hours and day(s) when you would like the rule to be active, and then click **Save**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3236cbb-event-intelligence-recurring-rules.png",
        "event-intelligence-recurring-rules.png",
        1712,
        484,
        "#f9f9f9"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Disable Event Rules"
}
[/block]
If you would like to pause an event rule’s activity, you can disable and re-enable it at a later time. This feature allows you to manually initiate integration-specific disablement during maintenance or testing on a tool. 

The Disable Rules functionality is part of our [Event Intelligence](https://support.pagerduty.com/v1/docs/event-intelligence) product, which is purchased separately from the core PagerDuty platform.

To temporarily disable a rule, go to **Configuration** :fa-arrow-right: **Event Rules**, then click the :fa-cog: dropdown next to the rule and click **Disable Rule**. While the rule is disabled, you will see a **Disabled** pill marker in the **Matching conditions** section of the rule. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8c693c2-event-intelligence-disable-rule.png",
        "event-intelligence-disable-rule.png",
        2192,
        420,
        "#f3f5f2"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/446e0f6-event-intelligence-disabled-marker.png",
        "event-intelligence-disabled-marker.png",
        1890,
        469,
        "#f9f9f9"
      ]
    }
  ]
}
[/block]
If you would like to enable the rule again, click the :fa-cog: dropdown and click **Enable Rule**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f3ef5d4-event-intelligence-enable-rule.png",
        "event-intelligence-enable-rule.png",
        2246,
        478,
        "#f4f6f3"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Threshold Alerts"
}
[/block]
Receive PagerDuty notifications only when your customized alert conditions breach your specified limits. In this way, responders effectively reduce alert noise without missing critical issues. 

The Threshold Alerts functionality is part of our [Event Intelligence](https://support.pagerduty.com/v1/docs/event-intelligence) product, which is purchased separately from the core PagerDuty platform.

Thresholds are set within Global Event Rules Engine workflows. Users first set specific rule criteria, which, if met, will be included in their threshold count.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e7d5da-New_Event_Rule_-_PagerDuty.png",
        "New_Event_Rule_-_PagerDuty.png",
        1748,
        664,
        "#f8f9f9"
      ]
    }
  ]
}
[/block]
Users can then select a service to route it to in the **Alert Behavior** section.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e9988b1-New_Event_Rule_-_PagerDuty.png",
        "New_Event_Rule_-_PagerDuty.png",
        1760,
        420,
        "#fcfcfc"
      ]
    }
  ]
}
[/block]
Once the service is selected, you will see an **Incident Behavior** section appear below. Here you can configure threshold alerting.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/725a1f9-New_Event_Rule_-_PagerDuty.png",
        "New_Event_Rule_-_PagerDuty.png",
        1898,
        320,
        "#fafafa"
      ]
    }
  ]
}
[/block]
In this example, if five alerts come in from host123 within a 10 minute time window, the threshold will be exceeded and a PagerDuty incident will be created. 

##Thresholds and Alert Grouping

PagerDuty’s Alert Grouping feature can be used in combination with Threshold Alerting in order to reduce the number of incidents created, minimize noise, and keep the responder focused on the issue. While Threshold Alerting determines how many alerts are required to create an incident and notify the on-call user, Alert Grouping can take this a step further by then grouping any alerts that exceed this threshold into a single, open incident. 

The current alert grouping options that are included with the Event Intelligence package are [Time-Based Alert Grouping](https://support.pagerduty.com/docs/time-based-alert-grouping) and [Intelligent Alert Grouping](https://support.pagerduty.com/v1/docs/intelligent-alert-grouping). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7095a5b-alert-grouping.png",
        "alert-grouping.png",
        1036,
        274,
        "#f5f7f8"
      ]
    }
  ]
}
[/block]
Users can view all alerts, including those that do not breach the set thresholds, in the Alerts table. Alerts not breaching the thresholds will appear in the table with a status of `Triggered (Suppressed)`. When the threshold is breached, the alert that exceeded the threshold will appear with a `Triggered` status. 

This alert will also create an incident, which can be viewed in the Incidents Table.
[block:api-header]
{
  "title": "Q&A:"
}
[/block]
###Are email integration filters/rules, or event transformers supported?
For events routed by the routing engine, service-level logic applies. Event transformers are currently not supported.

###Are events transformed into our Common Event Format (CEF)?
Events that are routed are transformed into CEF. Custom Event Transforms (CETs) are not supported.

###What happens to events that don’t match any rules?
Currently, any events that are sent through global event rules and do not match any rules are suppressed. You can find them in the alerts table. You can change this default behavior by editing the catch-all rule at the bottom of your rules list.

###Is there a way to bulk add/delete/edit these Global Routing rules?

Yes. You can leverage the [Global Event Rules API](https://v2.developer.pagerduty.com/v2/docs/global-event-rules-api) to create a script which will allow this functionality.

###Once an event is routed to a service from my global event rules, will the event rules I set up on my service be respected as well?

Yes. [Service-level event rules](https://support.pagerduty.com/docs/event-management#section-suppression-and-event-rules) can be used in conjunction with your global event rules this way.