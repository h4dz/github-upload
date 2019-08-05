---
title: "Intelligent Alert Grouping"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "body": "Please note that this feature is now currently available as part of the [Event Intelligence](https://support.pagerduty.com/v1/docs/event-intelligence) package or Enterprise plan. If you would like to sign up for a trial of this feature and other Event Intelligence features, contact Sales at [sales@pagerdutycom](https://www.pagerduty.com/contact-us/#contact-sales). If you have any questions or would like to share your thoughts and feedback, please reach out to our Support Team at [support@pagerduty.com](https://www.pagerduty.com/contact-us/#contact-support)."
}
[/block]

[block:api-header]
{
  "title": "Overview"
}
[/block]
When enabled on a service, Intelligent Alert Grouping will automatically add incoming alerts to related open incidents on that service to help keep responders focused on the problem at hand. Upon enabling a service to use Intelligent Alert Grouping, the first new incoming alert will create a new incident. The underlying algorithm will then determine which, if any, subsequent alerts should be grouped into existing incidents.  Once an incident is closed, no new alerts will be added to it. 

The Intelligent Alert Grouping algorithm includes a machine-learning based model that is uniquely trained on the history of alerts on each service. The algorithm observes the history of alerts grouped into incidents on a service either from responders manually merging or automatically generated groups from time-based alert grouping. The algorithm will adapt over time to understand new types of alerts and react to responder behavior. 
[block:api-header]
{
  "title": "How to Tell When an Incident is Grouping Alerts"
}
[/block]
When enabled, you can see Intelligent Alert Grouping actively grouping alerts on the details page of a specific incident. Grouped alerts will appear under the Alerts tab.

The alert grouping labels notify you that the incident is using alert grouping. This could mean either Time-Based Alert Grouping or Intelligent Alert Grouping. In this case, the alert grouping details indicates that this incident is adding alerts via Intelligent Alert Grouping. Beneath the incident title, you can also see the number of grouped alerts, as well as the time the most recent alert was added. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/512a9ba-alert_grouping_indicators.png",
        "alert_grouping_indicators.png",
        1267,
        978,
        "#f4f2f3"
      ],
      "caption": "(1) Triggered incident actively grouping using Intelligent Alert Grouping"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1eea35e-Alert_grouping_details.png",
        "Alert_grouping_details.png",
        648,
        399,
        "#eff0f0"
      ],
      "caption": "(2) Alert grouping details indicating Intelligent Alert Grouping is enabled"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Getting Started"
}
[/block]
##Recommended Services

Intelligent alert grouping is recommended on eligible services, indicated on the service details page, under the alert grouping tab. Intelligent alert grouping does not group alerts from different services together. 

To be recommended for intelligent alert grouping, a service must have alerts and incidents enabled. 

You can find whether a service is recommended or not on the service details page, under the alert grouping tab. If the service is configured to only create incidents, the Intelligent Alert Grouping option will be not be available. You can edit your service on the service configuration page to enable alerts and incidents. Please note that some integrations do not currently support alerts and incidents - you can read more about this [here](https://support.pagerduty.com/docs/alerts#section-bi-directional-integration-limitations). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/072b3be-IAG_tab_screenshot.png",
        "IAG_tab_screenshot.png",
        881,
        639,
        "#f4f6f5"
      ],
      "caption": "(2) Intelligent Alert Grouping option on a recommended service"
    }
  ]
}
[/block]
##Influencing the Algorithm

The Intelligent Alert Grouping algorithm is built to observe real alert data and incident history and adapt as new alerts are seen on the service. No explicit configuration is necessary, other than selecting the Intelligent Alert Grouping option. 

The best way for the algorithm to learn and adapt to new grouping behaviors is to manually merge incidents that are related, and to manually move alerts out of incidents when they are not related. For steps on how to merge incidents and move alerts, see [this Knowledge Base article](https://support.pagerduty.com/docs/editing-incidents#section-how-to-merge-incidents).

The algorithm interprets and adjusts new alert data periodically.  Any new data or behavior on a service may not be taken into consideration for up to a day when grouping new alerts.

We strongly recommend **against** sending in test data to try and influence the algorithm, as this can result in unpredictable behavior.
[block:api-header]
{
  "title": "Options"
}
[/block]
##Intelligently based on the alert content and past groups
Alerts are added intelligently to existing open incidents based on a machine learning model trained specifically on the historical data of your services. The grouping behavior adapts as you and your team use PagerDuty, learning from user behavior such as manually merging incidents together.

##For the following duration (time-based)
Groups all alerts for the specified time period while the incident is open. For more information, check out our [Knowledge Base article on Time-Based Alert Grouping](https://support.pagerduty.com/docs/time-based-alert-grouping).

##Do not group alerts automatically on this service
Default behavior. Alerts will not be automatically grouped. Inbound events will respect any dedupe keys sent in through the API.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5c050d6-Screen_Shot_2018-03-23_at_11.10.22_AM.png",
        "Screen Shot 2018-03-23 at 11.10.22 AM.png",
        899,
        376,
        "#879484"
      ],
      "caption": "(3) Grouping patterns for alerts without grouping, with Time-based Alert Grouping and Intelligent Alert Grouping"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "How Does Intelligent Alert Grouping Decide Which Alerts to Group?"
}
[/block]
The Intelligent Alert Grouping algorithm is designed to make conservative and reasonable alert groupings based on the previous groups of alerts on a service. The algorithm reacts to feedback from you and your team. For example, if you manually merge incidents together, the algorithm will learn to group those types of alerts together in the future.

If you find an incident has a group of alerts that does not match your expectations, you can manually move the alert to  a new incident or into other another existing incident. 

The Intelligent Alert Grouping algorithm starts by assuming less groups and waits for repeat examples of alert groups before it learns those alerts tend to be grouped. If alerts are new to the service, the algorithm may not group them until it has seen enough alerts of that type grouped into patterns. To help influence the algorithm, you can manually adjust the alert history and merge incidents or move alerts so that incident reflect accurate groups of alerts. 

For a walkthrough of how to manually merge alerts together, check out
[this Knowledge Base article](https://support.pagerduty.com/docs/editing-incidents#section-how-to-merge-incidents).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/90aa65a-manually_merge.png",
        "manually_merge.png",
        906,
        550,
        "#f3f3f4"
      ],
      "caption": "(4) How to manually move alerts to an existing or new incident"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d65fb31-Move_alert_new_incident.png",
        "Move_alert_new_incident.png",
        1044,
        573,
        "#8c8c8c"
      ],
      "caption": "(5) How to manually move alerts to a new incident, continued."
    }
  ]
}
[/block]
##How Intelligent Alert Grouping Works 

Intelligent Alert Grouping uses a machine-learning based algorithm that leverages both the alert data coming in to the system and the way human responders interact with the resulting incidents.

For the alert data, Intelligent Alert Grouping algorithm evaluates the content of the alert and when the alerts were triggered. For the responder behavior, the algorithm evaluates how responders acknowledge, resolve, and group incidents.

The strongest signal for the grouping algorithm is how alerts were previously grouped, based on automatic grouping (with time-based alert grouping), incidents that have been manually merged, and alerts that have been moved out of incidents. When not enough alerts have been grouped, we do our best to assume how alerts should be grouped based on other factors (like, how people respond to incidents that are open around the same time).

The data model is designed to react to real data that is created in real time. Test data tends to look and behave differently from real data, which is why we recommend not feeding your service with test data to influence the algorithm. The best way to provide feedback to the algorithm is to use PagerDuty to respond to real incidents with real people responding to those incidents.
[block:api-header]
{
  "title": "FAQ"
}
[/block]
###Can we expose the machine learning-based model via the API?
No, not at this time.

###Can I still manually merge incidents? 
Yes. Doing so will train the machine learning model to improve alert grouping for future incidents. 

###Can we plug our own machine learning code into PagerDuty?
No, not at this time.

###Does this take into account some of the rules or correlations we have configured outside of PagerDuty?
No, this model is entirely based on actions taken within PagerDuty.

###Does it affect the machine learning capabilities if I rename the service?
No, it does not. 

###What user role is this setting available to?
Once enabled on the account, the setting is available to anyone who can edit a service.

###Can Intelligent Alert Grouping group alerts together from multiple services?
Not at the moment. Intelligent Alert Grouping only looks at alerts from a single service. If you want alerts from different services to be grouped, you may need to reconfigure your service so that all related alerts are sent to the same service.

###Why didn’t my alerts get grouped together?
There might be many reasons the Intelligent Alert Grouping algorithm did not group alerts together. The most common reasons are that the alert might be too new to the service (the algorithm has never seen it before and isn’t sure how to group it), or there aren’t enough examples of that alert being grouped to make a confident decision that the alert should be grouped.

The Intelligent Alert Grouping algorithm takes into consideration several different factors, which makes understanding why alerts are grouped or not difficult to trace. If you believe that there has been enough history for an alert to be grouped, but are still noticing some unexpected grouping behavior, please reach out to support@pagerduty.com.

###Why don’t I see any alert grouping options on the Alert Grouping tab?
There could be a few reasons why you don’t see any options for alert grouping on this page
* **If you see only one option for no automatic grouping:** Your current pricing plan does not support any alert grouping options. If you are interested in trying alert grouping on any of your services, contact Sales at [sales@pagerdutycom](https://www.pagerduty.com/contact-us/#contact-sales) to start a free trial for Event Intelligence
* **If you see a message that the service is configured to incidents only:** This means that your service is able to create alerts, but it is not yet configured to do so. See [Enabling Alerts](https://support.pagerduty.com/docs/alerts#section-enabling-alerts) for steps on how to change your service settings.
* **If you see a message that the service has integrations that do not support alerts:** Some monitoring tools do not support creating alerts, and therefore any services with these tools integrated will not be able to take advantage of some advanced features such as alert grouping and event rules. To enable alerts on a service, you need to remove the integration that does not support alerts. For a list of integrations that do not support alerts please see [this article](https://support.pagerduty.com/docs/alerts#section-bi-directional-integration-limitations).

###Is there a limit to how many alerts can group into a single incident?

Yes - incidents are limited to 1000 alerts each. After this limit is reached, a new incident will be created and subsequent alerts will continue grouping under the new incident.