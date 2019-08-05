---
title: "Event Management"
excerpt: ""
---
[block:api-header]
{
  "title": "Reduce the Number of Notifications for the Same Incident/Event"
}
[/block]
Notification fatigue can be assuaged with the following actions:
- [Include an Incident Key in your API Call (for API-based services)](#section-include-an-incident-key-in-your-api-call)
- [Adjust your Email Management Settings (for email-based services)](#section-adjust-your-email-management-settings)

##Include an Incident Key in your API Call
If your service is set up as a service type and multiple incidents are triggering for the same issue, your team will be notified for each duplicate incident. To group these incidents you will want to include `incident_key` in your parameters for triggering incidents.

PagerDuty de-duplicates incidents based on the `incident_key` parameter — this identifies the incident to which a trigger event should be applied. If there are no open (unresolved) incidents with this key, a new incident will be created.
[block:callout]
{
  "type": "info",
  "body": "Depending on which version of the Events API you're using, you may also see this parameter referred to as `dedup_key`. Please read more about this in our [dev docs](https://v2.developer.pagerduty.com/docs/events-api-v2#alert-de-duplication).\n\nWith Alerts enabled on a service, this value is referred to as **Alert Key** in the web UI."
}
[/block]
If there is already an open incident with a matching key, this event will be appended to that incident's alert log as an additional **Trigger** log entry.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/29c6be9-Screen_Shot_2017-04-05_at_2.26.53_PM.png",
        "Screen Shot 2017-04-05 at 2.26.53 PM.png",
        1169,
        317,
        "#f8f8f8"
      ]
    }
  ]
}
[/block]
If the event key field isn't provided, PagerDuty will automatically open a new incident with a unique key.

##Adjust your Email Management Settings
If you have an [email integration](https://www.pagerduty.com/docs/guides/email-integration-guide/) you can change your incident creation settings so that incidents are only triggered under certain conditions.

There are four types of email management settings: 
- **Open a new alert/incident for each trigger email**: Each email sent to the service's email address will open a new incident.
- **Open a new alert/incident for each new trigger email subject**: Incidents are de-duped based on the subject of the trigger emails. For example, if two emails with the same subject are sent to this service's email address, the first opens a new incident, and the second is appended to this incident.
- **Open a new alert/incident only if an open incident does not already exist**: An email sent to the service's email address will only open a new incident if they service has no open incidents; otherwise, the email will be appended to the open incident.
- **Create and resolve alerts/incidents based on custom rules**: Use [regular expressions](/docs/email-management-filters-and-rules#section-advanced-email-management-extracting-information-with-regular-expressions) to parse incident triggers and resolves.

The last three incident creation settings are ones that allow alert/incident de-duplication and reduce the number of notifications being sent. 

To change the incident creation settings for your email integration service:
1. Go to **Configuration → Services**
2. Click on the name of the service that houses the integration, then select the **Integrations** tab. You can edit the integration by selecting **Edit** from the settings cog, or from the integration details page accessible by clicking the name of the integration.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f12bd44-RS_-_email_edit_2.png",
        "RS_-_email_edit_2.png",
        2174,
        426,
        "#403a3a"
      ]
    }
  ]
}
[/block]
3. Select the appropriate email management setting from the four options provided.
4. Click **Save changes**.

For more in-depth information about email management settings, please visit our article about [email filters and email management rules.](https://support.pagerduty.com/docs/email-management-filters-and-rules) 
[block:api-header]
{
  "title": "Email Size Limits, Truncation, and Attachments"
}
[/block]
##Email Truncation
If an email that triggered an incident is not displayed in its entirety in PagerDuty it may have been truncated due to its size.

If the email (including headers, attachments, etc.) is under 96 KB the message can pass through without truncation. If the message is over 96 KB the following can happen:
1. Any parts of the email body where the Content-Type are not matched by this regular expression will be discarded:
    `/(text\/(plain|html)|multipart\/)/`
This means PDF files and similar attachments will be stripped.
2. Text parts (Content-Type of `text/plain` or `text/html`) will be truncated to 32 KB.
3. If the resulting total email size (including headers, attachments, etc.) still exceeds 192 KB then we will reject the message.

You can tell if a message has been truncated or had attachments removed by checking for the headers `X-PagerDuty-Truncated-Part` or `X-PagerDuty-Removed-Attachments` when viewing the raw message. You can view the raw message on the incident's individual page by clicking **View Message** on an incident log entry, then **View Raw Message**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f9cdda-031b923-e1add0b-truncated.png",
        "031b923-e1add0b-truncated.png",
        595,
        142,
        "#e59441"
      ]
    }
  ]
}
[/block]
##Email Size Limits
If an email is over 10 MB, our server will reject it.

##Incident Key Truncation
If the incident key of the email that triggered an incident is more than 255 characters it will be truncated to 255 characters.

##Truncation of Incident Details in Email Notifications
When you receive a PagerDuty email notification, the "Details" section of each incident will be truncated to 500 characters. That said, the entire email body is accessible in the PagerDuty web UI via the incident logs and details, or via the mobile app.
[block:api-header]
{
  "title": "Suppression and Event Rules"
}
[/block]
Event Rules define automated actions to take on alerts created by services, based on conditions that apply to information in the inbound events' payloads. Event Rules can perform actions such as setting the severity of the resulting alert, or automatically suppressing the alert altogether.

Event Rules can be used on services that use vendor-specific and API-based integrations. For email integrations, we recommend utilizing [email management rules](/docs/email-management-filters-and-rules#section-trigger-and-resolve-alerts-with-email-management-rules).

- [Configure Event Rules For a Service](#section-configure-event-rules-for-a-service)
- [Event Rule Behavior](#section-event-rule-behavior)
- [Setting Conditions for Event Rules](#section-setting-conditions-for-event-rules)
- [Suppressing Alerts](#section-suppression)

##Configure Event Rules For a Service

To use event rules on a service, that service must first be set to create [Alerts and Incidents](/docs/alerts#section-getting-started-with-alerts-and-incidents) for inbound events. To do this, go to **Configuration → Services**, edit the service and locate the **Incident Behavior** section at the bottom of the Edit Service page.

Event Rules then can be added from the individual service page; the Event Rules tab is located on the far right.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/01081bb-suppress.png",
        "suppress.png",
        1064,
        454,
        "#2b754b"
      ]
    }
  ]
}
[/block]
##Event Rule Behavior
Rules are evaluated in the order they appear in the **Event Rules** configuration tab, top to bottom. The first matching rule is applied, and then execution stops. If no rule matches, the event is processed ordinarily, as if there were no rules configured.

The order of rules can be controlled by dragging and dropping the rules in the Event Rules page.

If an event rule is deleted while a suppressed alert is in a "triggered" state, further alerts with the same alert key will continue to deduplicate until the alert is resolved.

##Setting Conditions for Event Rules

When creating a rule, first set the conditions under which the rule will apply. For example:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f361d01-Screen_Shot_2017-03-28_at_3.43.20_PM.png",
        "Screen Shot 2017-03-28 at 3.43.20 PM.png",
        1144,
        424,
        "#eaeaea"
      ]
    }
  ]
}
[/block]
In the above example, the rule will apply to an inbound event if the value of its «Source» field is exactly `prod05-nginx`. This particular rule will cause the event to be suppressed, and the severity will be set to Error.

Event rule conditions can be configured for any of the following [PagerDuty Common Event Format (PD-CEF)](doc:pd-cef) fields:
- **Class**
- **Component**
- **Group**
- **Severity**
- **Source**
- **Summary**
- **Custom Details**
[block:callout]
{
  "type": "info",
  "title": "Accessing Custom Details",
  "body": "In order to access nested components of the custom details property for a comparison in a condition, enter the full namespace path, in dot notation, from the root of the details property, into the **Key name in details** field. For example, if the details property is `{\"foo\": {\"bar1\":\n {\"baz\": \"thevaluehere\"}, \"bar2\": 2}}`, the value in the comparison for `foo.bar1.baz` would be `thevaluehere`."
}
[/block]
Once you have selected a field to examine, select a condition, such as equals or contains, and (if applicable) enter a value to compare the field against. 

In addition to basic comparison, regular expressions can be used. Note, PagerDuty uses the [RE2](https://github.com/google/re2/wiki/Syntax) flavor of RegEx to evaluate expressions.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dadc376-image6.png",
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
        "https://files.readme.io/4a7b9cd-image2.png",
        "image2.png",
        522,
        223,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]
##Suppression
Suppression, as opposed to setting the severity of alerts, allows you to send events to PagerDuty without triggering any notifications. Suppressed alerts are stored in PagerDuty and available for forensics, analysis, and context, but do not create incidents. Suppressed alerts can be viewed in the alerts list as well as the [Infrastructure Health Application](doc:operations-command-console#section-infrastructure-health-application).

To suppress an alert if it matches a given set of conditions, select «Suppress» as the action to take when you are building your Event Rules.

###Viewing Suppressed Alerts
Suppressed alerts are filtered out of the incidents dashboard by default, including the incidents page for the service on which the suppressed alerts were triggered. Moreover, because suppressed events do not trigger incidents, they will not be visible in the mobile app.

They can be viewed in the Alerts tab at the top of your screen, between Incidents and Configuration.

Here is an example of a suppressed event. It looks very similar to other alerts, but has "Suppressed" in the severity field and is not assigned/assignable.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/45a8fa0-the_alert.png",
        "the_alert.png",
        987,
        552,
        "#f0f0f0"
      ]
    }
  ]
}
[/block]
The incident below was triggered on a service with alerts set up to trigger as suppressed by default.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/da598f2-suppressed_event.png",
        "suppressed_event.png",
        687,
        720,
        "#f3f3fa"
      ]
    }
  ]
}
[/block]
###Infrastructure Health Application  
Suppressed alerts may also be viewed in the [Infrastructure Health Application](doc:operations-command-console#section-infrastructure-health-application). Suppressed alerts will be shown in gray to differentiate them from the rest of your alerts and incidents.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/687dfec-dark_mode.png",
        "dark mode.png",
        2230,
        1286,
        "#131c2c"
      ]
    }
  ]
}
[/block]