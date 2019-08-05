---
title: "Triage Major Incidents & Integrate Your ITSM Toolchain"
excerpt: ""
---
[block:api-header]
{
  "title": "Overview"
}
[/block]
PagerDuty’s response orchestration capabilities are essential tools for responding to major incidents - whether it’s mobilizing the initial response team, augmenting the response with additional experts, or keeping stakeholders informed. Knowing when to engage a coordinated response, and being able to use these capabilities for all major incidents regardless of where they originate, are key elements of modern incident management process.

This guide reviews how to set up an incident classification scheme for triage, how to use incident classification within PagerDuty, and how to integrate with an ITSM toolchain so that all incidents take advantage of PagerDuty’s response orchestration capabilities.
[block:api-header]
{
  "title": "Establish an incident classification scheme"
}
[/block]
Ideally shared organization-wide, your incident classification scheme establishes common language and criteria for working with, and communicating about, incidents. It’s helpful to keep in mind that this scheme is not just for technical responders and support staff - other parts of your organization may need to be aware of incidents and their assessed impact and occasionally need to participate in incident response, as well.

There are several parts to establishing an incident classification scheme:
  * List the incident classification levels. This is frequently P1 through P5 (for priority), or SEV-1 through SEV-5 (for severity). Typically, the lower the number, the bigger the impact it indicates.
  * Define what each level means: Describe the incident impact and characteristics that apply for each classification level. These guidelines must be clear and objective enough that responders can accurately assess an open incident and assign exactly one level to it, although the incident may be “upgraded” or “downgraded” as the situation evolves.
  * Define the expected response: For each classification level, the expected scope and response urgency must be identified. Some organizations have a formal or informal service level agreement per level, as well.

For an example and additional details on the above, see the PagerDuty [Incident Response Guide](https://response.pagerduty.com/before/severity_levels/).

Many organizations already have an incident classification scheme in place. If you don’t, putting in place a small number of classification levels is essential for an effective triage and major incident response process.  If, on the other hand, you have more than 5 or 6 classification levels, think critically about how many levels would benefit your organization in practice. The more levels you have, the more complex and time-consuming triage becomes.
[block:api-header]
{
  "title": "Configure your incident classification levels in PagerDuty"
}
[/block]
When you have identified the classification levels you will be using, the next step is to configure PagerDuty to support those levels. First, a PagerDuty administrator user must [enable the Incident Priority feature](https://support.pagerduty.com/docs/incident-priority#section-enabling-incident-priority) on your account.

Next, you’ll want to customize the levels themselves. In addition to specifying the name for each level, you can also provide triage guidance to responders in the description. 

Finally, each level has a color associated with it, which can be used to draw attention to the most important incidents in a dashboard or other view. It’s best to use distinctive colors for the levels corresponding to major incidents for immediate recognition and visibility. For example, at PagerDuty we use red and orange for our two highest levels, and then gray and blue variations for lesser incident levels:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ceee92-Screen_Shot_2017-12-07_at_3.14.36_PM.png",
        "Screen Shot 2017-12-07 at 3.14.36 PM.png",
        1892,
        812,
        "#365561"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Prioritize incidents during triage"
}
[/block]
Prioritizing incidents helps drive decisions around the response process and also provides valuable context for other people. When looking at an incident, the priority gives an immediate and clear indication of prior assessment that has been performed. This is what an incident looks like with priority level set:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4c45e45-Screen_Shot_2017-12-07_at_3.16.14_PM.png",
        "Screen Shot 2017-12-07 at 3.16.14 PM.png",
        1890,
        610,
        "#e2e2df"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
In addition, priority is clearly displayed on the incident dashboard, making it easy to see when critical issues are active. You can sort incidents by priority on this page, so that whether looking at incidents for a single team or across your whole organization, you can instantly see critical issues:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ae5b3fb-Screen_Shot_2017-12-07_at_3.17.40_PM.png",
        "Screen Shot 2017-12-07 at 3.17.40 PM.png",
        1890,
        822,
        "#f3f3f3"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Using incident priority with scripts and external automation"
}
[/block]
In addition to the features available within the PagerDuty web app, incident priority can also be used in automated systems. The incident REST API can be used to specify the priority for an incident when it is created, and all relevant priority details are included with incident objects returned from the API. You can learn more about how to [retrieve the configured incident priority scheme](https://v2.developer.pagerduty.com/v2/page/api-reference#!/Priorities/get_priorities) and [create incidents with priority](https://v2.developer.pagerduty.com/v2/page/api-reference#!/Incidents/post_incidents) in our developer documentation.

Additionally, incident webhooks include full information about that incident’s priority; details are available [here](https://v2.developer.pagerduty.com/docs/webhooks-v2-overview).
[block:api-header]
{
  "title": "Integrating PagerDuty incident response with ITSM tools"
}
[/block]
ITSM tools typically excel at ticketing-related workflows and are used to create and track all customer- and service desk- reported incidents. However, ITSM tools usually don’t have effective response capabilities, particularly for critical impact incidents requiring urgent response.
Because of this, a common set-up is to use PagerDuty’s extensive incident response capabilities to augment an ITSM tool deployment. In this configuration, certain incidents in the ITSM tool are synchronized into PagerDuty, at which point PagerDuty’s coordinated response and stakeholder communication facilities can be leveraged.

PagerDuty integrates with a number of ITSM tools, including:
  * [ServiceNow](https://support.pagerduty.com/docs/servicenow)
  * [ServiceNow Express](https://www.pagerduty.com/docs/guides/servicenow-express-integration-guide/)
  * [Remedy](https://www.pagerduty.com/docs/guides/bmc-service-desk-integration-guide/)
  * [JIRA](https://www.pagerduty.com/docs/guides/jira-webhook-email-integration-guide/)

Many of the ITSM tool integrations also synchronize PagerDuty incident changes back to the originating ticket in the ITSM tool; these synchronized changes include escalations, re-assignments, priority changes, state changes, and notes.
[block:api-header]
{
  "title": "Integrating monitoring tools and ITSM systems via PagerDuty"
}
[/block]
ITSM systems often don’t integrate well with monitoring tools, as they are inherently designed to work with “human-speed” data, rather than the “machine-speed” data flows that monitoring tools generate. In cases where ITSM systems are used with monitoring tools, it often results in a “swivel-chair” workflow: in this form of “integration,” a user works directly with a monitoring tool; then when they determine an incident is occurring, they switch applications and manually create a ticket in the ITSM system, using clipboard cut-and-paste to move the data over. This workflow is cumbersome, error-prone, and provides no direct linkage between operational data and ITSM tickets.

Using PagerDuty to integrate monitoring tools and ITSM systems results in a much better workflow. [Integrating a monitoring tool](https://support.pagerduty.com/docs/services-and-integrations#section-add-integrations-to-an-existing-service) with PagerDuty is extremely simple, and can often be completed in just a few minutes. Once the monitoring tool is integrated, alerts will flow into PagerDuty, where they can be routed to services, have event rules applied, be filtered out if appropriate, and much more. As well, any alert that requires attention will be automatically assigned to the appropriate responder according to scheduled on-call rotations. For straightforward issues, the initial responder can handle the issue directly; in other cases the responder will triage the incident and classify it using the established incident priority levels.

At this point many organizations will want to have an ITSM ticket created to track the incident. Instead of manually creating the ticket, the responder can simply click a button within PagerDuty to create the ITSM ticket.

After the ITSM ticket is created, the PagerDuty incident and ITSM ticket are linked, and updates to the PagerDuty incident will be reflected in the ITSM ticket. This is beneficial in many ways:
  * Incident response orchestration: PagerDuty has response mobilization, stakeholder communication, and other response orchestration capabilities, all of which can be leveraged directly from the PagerDuty incident.
  * Data linkage: For review and reporting purposes, the ITSM ticket is linked to the PagerDuty incident, which in turn is linked to the underlying monitoring tool alerts. This linkage makes post-incident analysis, including postmortems, much more efficient.
  * Auto-resolution: If the monitoring tool detects that the underlying issue has recovered, the corresponding PagerDuty incident will receive this update, resolve itself, and then reflect that resolution to the ITSM ticket.
  * Minimized noise: The right tickets are created in the ITSM system, rather than too many (if monitoring tool alerts are fed directly in) or too few (if manual ticket creation is the norm).

PagerDuty’s [ServiceNow](https://www.pagerduty.com/docs/guides/servicenow-integration-guide/) and [JIRA](https://www.pagerduty.com/docs/guides/jira-software-extension-guide/) extensions support this type of managed integration with ITSM systems, with support for additional ITSM systems coming in the future.
[block:api-header]
{
  "title": "Summary"
}
[/block]
You can find additional information about the PagerDuty features mentioned in the following Knowledge Base Articles:
  * [Priority](https://support.pagerduty.com/docs/incident-priority)
  * ITSM Integrations: ServiceNow, Remedy, JIRA

For a detailed overview on establishing best practices, as well as more examples on how you can leverage PagerDuty’s capabilities, please refer to our [Incident Response Guide](https://response.pagerduty.com/). We also recommend reviewing the following how-to guides, which cover additional major incident response topics:
  * [Mobilize a Coordinated Response](https://support.pagerduty.com/docs/how-to-mobilizing-coordinated-responses)
  * [Communicate Effectively with Stakeholders](https://support.pagerduty.com/docs/how-to-effective-stakeholder-communications)