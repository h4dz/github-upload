---
title: "Preview Intelligent Alert Grouping"
excerpt: ""
---
Before enabling [Intelligent Alert Grouping](https://support.pagerduty.com/docs/intelligent-alert-grouping) on a service, your team may want to understand how alerts will be grouped into incidents. Preview Intelligent Alert Grouping allows you to see how your own alerts would have been automatically grouped. 

Preview Intelligent Alert Grouping does not change how alerts are actually grouped into incidents. It is only a preview, and cannot be applied retroactively on real alerts. To learn how to change how alerts are grouped into incidents, see [Editing Incidents](https://support.pagerduty.com/docs/editing-incidents#section-how-to-merge-incidents).
[block:callout]
{
  "type": "info",
  "body": "This feature is currently available on accounts with [Event Intelligence](https://support.pagerduty.com/docs/event-intelligence) or on the Enterprise plan. If you have any questions or feedback, please reach out to [support@pagerduty.com](https://www.pagerduty.com/contact-us/#contact-support)."
}
[/block]

[block:api-header]
{
  "title": "How to Access the Preview"
}
[/block]
At the moment, Intelligent Alert Grouping can only be configured at the service level, so to preview Intelligent Alert Grouping, first select an appropriate service. One of the main benefits of Intelligent Alert Grouping is reducing alert noise, so services with interesting and meaningful previews tend to be services with a high volume of incidents with some variance in their incident titles. 

When you have identified a service, go to the service details page, then click the Alert Grouping tab. The Alert Grouping tab displays the available alert grouping options available on that service based on your pricing plan. If you do not see Intelligent Alert Grouping as an option, you can contact Sales at [sales@pagerdutycom](https://www.pagerduty.com/contact-us/#contact-sales) to start a free trial of Event Intelligence.

If you see Intelligent Alert Grouping as an option, but you do not see a Preview Intelligent Alert Grouping button, your service has not had a preview calculated yet. See the [FAQ](#section-faq) for possible reasons.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0935c67-preview_iag_alert_tab.png",
        "preview_iag_alert_tab.png",
        1914,
        1420,
        "#e7e8e9"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Viewing Groups in Detail"
}
[/block]
The preview modal provides a rich view of how alerts would have been grouped into incidents on your service over a given period of time. Previews are generated once a day and are based on alerts and incidents from the two weeks before the date the preview was generated. 

At a high level, you can start to understand the value of enabling Intelligent Alert Grouping on your service in terms of the number of incidents that were actually triggered, and how many fewer incidents your team would have been notified for, had Intelligent Alert Grouping been enabled. To learn more about how the Intelligent Alert Grouping algorithm works, please see [this article](https://support.pagerduty.com/docs/intelligent-alert-grouping#section-how-does-intelligent-alert-grouping-decide-which-alerts-to-group).

You will see three metrics at the top of the preview, which are all calculated based on the given time frame: 

**Fewer Incidents:** Reflects the difference in the number incidents created if Intelligent Alert Grouping had been enabled compared to if it hadn’t. 

**Current Incidents:** The number of current incidents created on the service with the current alert grouping setting. 

**Potential Incidents:** Reflects the number of potential incidents that would have been created with Intelligent Alert Grouping enabled, each with their own grouped alerts.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a14f57-preview_iag_modal.png",
        "preview_iag_modal.png",
        973,
        1067,
        "#e8e7e7"
      ]
    }
  ]
}
[/block]
You can expand each potential incident to see how many and which alerts would have been grouped into the potential incident. The date and time listed reflect when the alert was triggered. Please note that the title of the potential incident is derived from the first incoming alert. 

Some services may have a lot of potential incidents in this list. We recommend looking at some of the larger groups to get a sense of the grouping behavior of the algorithm.
[block:api-header]
{
  "title": "FAQ"
}
[/block]
###I just triggered an incident/alert, why is it not appearing in the preview?
Previews are not generated in real time, they are generated once a day. If you have new alert data that you’d like the preview to take into account, we recommend checking back in 24 hours to see if preview has been regenerated. 

###When will the preview on my service be updated?

New previews are calculated once a day, as long as there have been enough alerts and incidents within the last few months. If a preview on your service is more than a day old, it could be because the Intelligent Alert Grouping algorithm doesn’t have enough data or isn’t seeing enough patterns in the data to generate a new preview.

At the moment, old previews will only be purged when a new preview is available to replace it.

###There are some alerts appearing under potential incidents that I wouldn’t want to be grouped together - how can I adjust these groups?
While the preview is static and cannot be changed directly, you can still provide feedback on the quality of the groups you see and this feedback will help the algorithm learn and create better groups.

To provide feedback on the groups, go to the original incident and move the alert out, or merge incidents together. For steps on how to do this, see [Editing Incidents](https://support.pagerduty.com/docs/editing-incidents#section-how-to-merge-incidents).

Once you provide feedback, your changes will not be immediately reflected in the current preview. You may notice a difference the next time the preview is generated.

###One of my services is set to create incidents only (not alerts). Can I still use alert grouping and preview intelligent alert grouping?
Alert grouping options are available only if the service has alerts and incidents enabled. As long as you are using integrations on that service that support alerts, you can change your service settings to enable alerts and incidents. See [Enabling Alerts](https://support.pagerduty.com/docs/alerts#section-enabling-alerts) for steps on how to change your service settings. 

Once the service is set to create alerts and incidents, you will immediately see all alert grouping options available to you on your account’s pricing plan. You can still preview Intelligent Alert Grouping and the preview will be calculated based on the incidents on that service. You may see some slightly different behavior in the preview, such as a link to the original incident instead of the original alert.