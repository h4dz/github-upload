---
title: "IXON Cloud Integration Guide | PagerDuty"
excerpt: ""
---
#PagerDuty + IXON Cloud Integration Benefits

* Notify on-call responders based on alerts sent from IXON Cloud.
* Send enriched event data from IXON Cloud including customized long content.
* Create high and low urgency incidents based on the systemLabel of the event from the IXON Cloud event payload using Event Rules.

#How it Works

* IXON Cloud uses webhooks to send HTTP POST message events to an endpoint in PagerDuty. 
* When PagerDuty receives HTTP POST message events, it will trigger an incident to notify users on-call.

#Requirements

* This integration requires a [Manager role](https://support.pagerduty.com/docs/advanced-permissions#section-object-roles) or higher for the service your IXON Cloud integration is integrated with. If you do not have this role, please reach out to an admin or Account Owner within your organization to configure the integration. 

#Integration Walkthrough
##In PagerDuty
1. From the **Configuration** menu, select **Services**.
2. **If you are adding your integration to an existing service**, click the name of the service you want to add the integration to. Then select the **Integrations tab** and click the **New Integration** button and continue to step 3.
**If you are creating a new service** for your integration, please read our documentation in section [Configuring Services and Integrations](https://support.pagerduty.com/docs/services-and-integrations#section-configuring-services-and-integrations) and follow the steps outlined in the [Create a New Service](https://support.pagerduty.com/docs/services-and-integrations#section-create-a-new-service) section, selecting Custom Event Transformer as the **Integration Type** in step 4. Continue with Step 6 (below) once you have finished these steps.
[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
3. Enter an **Integration Name** in the format `monitoring-tool-service-name` (e.g. IXON-Cloud-Shopping-Cart) and select  Custom Event Transformer from the **Integration Type** menu.
4. Click **Add Integration** button to save your new integration. You will be redirected to the Integrations tab for your service.
5. In the same **Integration** tab, select the gear icon next to your IXON-Cloud integration under **Actions** and select **Edit**.
6. Within **The code you want to execute** field, input the following code and select **Save Changes**:
 
```
var input = PD.inputRequest.body;
var normalized_event = { 
event_type: PD.Trigger, 
description: input.shortContent, 
client: "IXON Cloud", 
client_url: "https://connect.ixon.cloud/messages/", 
details: input 
};
PD.emitGenericEvents([normalized_event]); 
```
7. An **Integration URL** will be generated on this screen. Keep this key saved in a safe place, as it will be used when you configure the integration with IXON Cloud in the next section.
[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
 
##In IXON Cloud
1. Open the **Messages** page and select the :fa-cog: for the **Settings** page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0857e58-ixon-messages.png",
        "ixon-messages.png",
        900,
        331,
        "#f9f5e3"
      ]
    }
  ]
}
[/block]
2. On the next screen, select **Add new webhook**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba7f613-IXON-Add_Webhook.png",
        "IXON-Add_Webhook.png",
        900,
        542,
        "#bbb8a9"
      ]
    }
  ]
}
[/block]
3. Enter a  **Name** for the webhook that describes its function, and input the **Integration URL** generated in step 7 of Integrating With a PagerDuty Service, above. Select **ADD** to save the webhook.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6ed32b0-ixon-add-completed-webook.png",
        "ixon-add-completed-webook.png",
        900,
        337,
        "#b5b3a9"
      ]
    }
  ]
}
[/block]
4. Return to the main IXON Cloud screen and submit a test alarm. To submit a test you will need a IXrouter or IXagent connected to the IXON Cloud.
Connect a device (most of the time a PLC or HMI) to your IXrouter or the device running the IXagent software. The device must support one of the following protocols: LoggerAPI, Modbus, Siemens S7-300/400/1200/1500, OPC Unified Architecture or EtherNet/IP.
Create a Data Source with this protocol for the IXrouter or IXagent and add variables to it. These variables contain the value of their counterparts in the PLC or HMI. 
Create Tags in the Cloud Notify app. These tags define when an alarm is triggered. For example `alarm_1` triggers when `variable_1` has a value of **true**. 
Trigger an Alarm by setting the value of `variable_1` to **true** in the PLC or HMI to send a webhook to PagerDuty.
To verify that a message is created and a webhook is sent to the integration URL endpoint, return to the PagerDuty web app and ensure that an incident has been created. If an incident has not been created, please verify that you have input the Integration URL correctly and submit another test alarm.

#FAQ

##Can I use Global Event Rules with the IXON Cloud integration? 

At this time it is not possible to use Global Event Routing, as the integration requires use of a Custom Event Transformer built into the integration.