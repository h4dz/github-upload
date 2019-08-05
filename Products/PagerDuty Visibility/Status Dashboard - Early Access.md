---
title: "Status Dashboard — Early Access"
excerpt: ""
---
PagerDuty’s Status Dashboard provides technical responders, business responders, and leaders a live, shared view of system health to improve awareness of operational issues. It displays the current status of key business services and sends notifications to alert users when business services are impacted. This feature improves communication between response teams and stakeholders during incidents. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b2111a6-status-dashboard-overview.png",
        "status-dashboard-overview.png",
        1286,
        1073,
        "#ebe2e2"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Status Communications is currently available in an Early Access phase. Please contact your account representative if you are interested in participating during this phase of the product.",
  "title": "Note"
}
[/block]

[block:api-header]
{
  "title": "Product Capabilities"
}
[/block]

##Status Dashboard

Designed with business stakeholders in mind, the Status Dashboard provides an overview of your business services' status, showing you at a glance whether any are being affected by incidents. A business service will appear as disrupted on the Status Dashboard when there is an open incident on any supporting technical service mapped to it and the incident has a priority assigned. When there are no incidents with priority open on any of the supporting technical services, then the business service will show as operational on the Status Dashboard.

##Multiple Dashboard Views 

Admins & Owners can now create multiple named dashboard views in your account. This allows you to create dashboards for different business units or teams. Right now you can only select from 'top level' business services to build your dashboards, but within the next week we will be adding the ability for you include any business services regardless of their hierarchy position.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/568b3ec-status-dashboard-multiple-dashboards-dropdown.png",
        "status-dashboard-multiple-dashboards-dropdown.png",
        1482,
        948,
        "#e7e8e6"
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
        "https://files.readme.io/8b5b249-status-dashboard-multiple-views.png",
        "status-dashboard-multiple-views.png",
        1612,
        1118,
        "#e9eaea"
      ]
    }
  ]
}
[/block]
##Limited Stakeholder Access Level

The new Limited Stakeholder access level provides access to view and subscribe to the status dashboard, and does not show any other parts of PagerDuty. This access level is great for teams who don't need to see all of the alerts, schedules, and responder details in your account. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b1a72a4-Screen_Shot_2019-07-12_at_11.43.18_am.png",
        "Screen Shot 2019-07-12 at 11.43.18 am.png",
        1486,
        958,
        "#e8ebe8"
      ]
    }
  ]
}
[/block]
To set up a Limited Stakeholder user, go to **Configuration** :fa-arrow-right: **Users** :fa-arrow-right: **Permissions & Teams**. The Limited Stakeholder option is listed under the **Fixed** roles. Speak to your account rep if you want to purchase more Stakeholder licenses in our new, lower cost packages.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/444ceee-status-communications-add-limited-stakeholder.png",
        "status-communications-add-limited-stakeholder.png",
        1538,
        616,
        "#e2e3e4"
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
        "https://files.readme.io/ff7fe02-status-communications-change-to-limited-stakeholder.png",
        "status-communications-change-to-limited-stakeholder.png",
        1566,
        1062,
        "#e9e9ea"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Configure Status Dashboard"
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "Admin roles, Global Admin and Account Owner base roles.\n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]
To configure the status dashboard, you must:

- [Step 1: Create business services](https://support.pagerduty.com/docs/status-communications-closed-beta#section-step-1-create-business-services) 
- [Step 2: Enable incident priority in your account](https://support.pagerduty.com/docs/status-communications-closed-beta#section-step-2-enable-incident-priority-in-your-account)

##Step 1: Create Business Services

Ideally, business services are:

- Recognizable to non-technical stakeholders
- Supported by one or more technical services in PagerDuty
 
You may have business services listed on an external status page, within a service catalog/CMDB, or defined in relation to existing health metrics from a monitoring tool.

1. Go to **Configuration** and select **Business Services**.
2. Click **Create New Business Service**.
3. Enter a meaningful name that will be recognizable to non-technical stakeholders and provide a description.
4. Enter the owner as yourself or a point of contact for the business service. *(Optional)*
5. Under **Services this business service depends on**, add any applicable service that would impact this business service. This will allow you to see which business services are affected by an incident within the Status Dashboard. **Note**: Sometimes there is a technical service that supports a business service but that is not critical to its function. You may prefer to omit **non-critical technical services** that support a business service, since a disruption to one of those technical services does not necessarily mean that the business service is disrupted.
6. Select **Save Changes to this Service** to create the service.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "While it is possible to configure multiple levels of business service dependencies, only the top level business services currently appear on the Status Dashboard. A “top level” business service is a business service with zero **Services relying on this business service** (see image below for an example). We will be expanding this functionality in coming iterations."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/71d4e8d-status-communications-business-service-config.png",
        "status-communications-business-service-config.png",
        1372,
        640,
        "#f4f6f4"
      ]
    }
  ]
}
[/block]
##Step 2: Enable Incident Priority in Your Account 

Next, follow the instructions in our section on [enabling incident priority](https://support.pagerduty.com/docs/incident-priority#section-enabling-incident-priority). Only incidents with an assigned priority will appear on your Status Dashboard. 

##Updating Business Service Status

During an incident, responders can update the status of a business service to indicate its disruption to business stakeholders via the Status Dashboard.  A business service will appear as disrupted on the Status Dashboard in two circumstances: 

1. When there is an open incident on any supporting technical service mapped to the business service and the incident has a [priority](https://support.pagerduty.com/docs/incident-priority) assigned. 

2. When an open incident has been manually associated with a business service and the incident has a [priority](https://support.pagerduty.com/docs/incident-priority) assigned. Responders can manually associate an incident with a business service by selecting the appropriate business service under the **Impacted Business Services** dropdown, found in the **Status Updates** tab of **Incident Details**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4bb2ca8-image3.png",
        "image3.png",
        1999,
        1206,
        "#f1f1f1"
      ]
    }
  ]
}
[/block]
Incidents that have not been assigned a priority will not appear on the Status Dashboard, so that it does not become cluttered with operational noise. When the above criteria are not met, the business service will show as operational on the Status Dashboard.

##Subscribing to Business Services

Business stakeholders can subscribe to business services they care about to stay informed about those services. Any user who subscribes to a business service will receive a notification whenever it is impacted by an ongoing incident and whenever a status update is posted about that incident. These notifications are sent via email, SMS, or push, depending on the user’s preferences. All status updates also appear on the Status Dashboard.

To subscribe to a business service, navigate to the **View My Subscriptions** page via the Status Dashboard. Select any business services you wish to subscribe to. Notifications will be sent to all email, SMS, and push notification channels you have set up in PagerDuty.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c1afbd9-status-dashboard-view-my-subscriptions.png",
        "status-dashboard-view-my-subscriptions.png",
        1419,
        441,
        "#edf5ed"
      ]
    }
  ]
}
[/block]
#Status Dashboard Early Access FAQ 

##How can I set incident priority automatically?

There are three ways to set incident priority: 

1. Set priority manually from the web or mobile app (see instructions [here](https://support.pagerduty.com/docs/incident-priority)).
2. Set priority via the REST API (see documentation [here](https://api-reference.pagerduty.com/#!/Incidents/post_incidents)). You can use [this](https://api-reference.pagerduty.com/#!/Priorities/get_priorities) endpoint to get your **priority_id** values. 
3. Set priority via Event Routing. You need the Event Intelligence add-on product or an Enterprise subscription to access this feature. This feature is not documented in the Knowledge Base yet —please reference this screenshot:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d176638-status-dashboard-priority-event-rule.png",
        "status-dashboard-priority-event-rule.png",
        596,
        693,
        "#f6f2f2"
      ]
    }
  ]
}
[/block]