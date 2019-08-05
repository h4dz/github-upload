---
title: "Amazon CloudWatch Integration Guide | PagerDuty"
excerpt: "Integration Guide for Amazon CloudWatch"
---
#Integration Overview 

Amazon CloudWatch provides monitoring for AWS resources and customer-run applications. The service can collect data, gain insight, and alert users to fix problems within applications and organizations. Amazon CloudWatch gives system-wide visibility into resource utilization and notifications can be set for when any metrics cross a specified threshold. These alarms can be automatically sent to PagerDuty, which then reliably alerts the correct on-call person through their preferred contact methods.

Follow the instructions below to configure your Amazon Cloudwatch with PagerDuty. Note that this integration expects to find in the `Message` property a nested JSON-encoded object; if this is not received, no alert will trigger. If you have any questions or need any assistance, please contact our support team at <a href="mailto:support@pagerduty.com">support@pagerduty.com</a>.

# In PagerDuty 

There are two ways that Amazon CloudWatch can be integrated with PagerDuty: via Global Event Routing or through an integration on a PagerDuty Service.

##Integrating with Global Event Routing

Integrating with Global Event Routing may be beneficial if you want to build different routing rules based on the payload coming from AWS. If you would like to learn more, please visit our article on [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing). 

1. From the **Configuration** menu, select **Event Rules**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f65feb3-PHD-Event-Rules.png",
        "PHD-Event-Rules.png",
        1780,
        1114,
        "#b8bbc0"
      ]
    }
  ]
}
[/block]
2. On the Event Rules screen, copy your **Integration Key**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ca92bbe-PHD-Global-Event-Rules-Key.png",
        "PHD-Global-Event-Rules-Key.png",
        2222,
        1184,
        "#f8f8f7"
      ]
    }
  ]
}
[/block]
3. Once you have your **Integration Key**, the **Integration URL** will be:

`https://events.pagerduty.com/x-ere/[YOUR_INTEGRATION_KEY_HERE]`

You can now proceed to the [In the AWS Management Console](https://support.pagerduty.com/v1/docs/aws-cloudwatch-integration-guide#section-in-the-aws-management-console) section below. 

##Integrating with a PagerDuty Service

Integrating with a PagerDuty Service directly can be beneficial if you don’t need to route alerts from AWS to different responders based on the event payload. You can still use [service-level event rules](https://support.pagerduty.com/docs/event-management#section-configure-event-rules-for-a-service) to perform actions such as suppressing.

1. From the **Configuration** menu, select **Services**.
2. On your Services page: If you are creating a new service for your integration, click **+Add New Service**. It is recommended that you create a service specifically for Amazon CloudWatch notifications.

If you are adding your integration to an existing service, click the name of the service you want to add the integration to. Then click the **Integrations** tab and click the **+New Integration** button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f6453e-AWS-CloudWatch-Add-New-Service.png",
        "AWS-CloudWatch-Add-New-Service.png",
        1688,
        790,
        "#b2b7bb"
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
        "https://files.readme.io/104a430-GuardDuty-New-Integration.png",
        "GuardDuty-New-Integration.png",
        1652,
        200,
        "#f2f8f2"
      ]
    }
  ]
}
[/block]
3. Select Amazon CloudWatch from the** Integration Type** menu and enter an **Integration Name**.
If you are creating a new service for your integration, in General Settings, enter a **Name** for your new service. Then, in Incident Settings, specify the** Escalation Policy**, **Notification Urgency**, and **Incident Behavior** for your new service.
4. Click the **Add Service** or** Add Integration** button to save your new integration. You will be redirected to the Integrations page for your service.
5. Copy the** Integration URL** for your new integration.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8de8509-AWS-CloudWatch-Integration-URL.png",
        "AWS-CloudWatch-Integration-URL.png",
        1692,
        384,
        "#f5f2f2"
      ]
    }
  ]
}
[/block]
# In the AWS Management Console

1. In the SNS console, click **Create Topic**. This will be used to route alerts to PagerDuty from AWS.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/69c2fe5-AWS-CloudWatch-SNS-Create-Topic.png",
        "AWS-CloudWatch-SNS-Create-Topic.png",
        1701,
        654,
        "#f7f7f7"
      ]
    }
  ]
}
[/block]
2. Enter a **Topic name** and **Display name**, then click **Create topic**. You may want to name your topic after your PagerDuty service’s name.
3. Now that your topic has been created, click **Create Subscription**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/38eae3d-AWS-CloudWatch-Create-Subscription.png",
        "AWS-CloudWatch-Create-Subscription.png",
        1558,
        344,
        "#edecec"
      ]
    }
  ]
}
[/block]
4. Make sure **HTTPS** is the selected Protocol. Paste your **Integration URL** from step 5 (above) into the **Endpoint** field and click **Create Subscription**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eee14a9-GuardDuty-Create-Subscription-2.png",
        "GuardDuty-Create-Subscription-2.png",
        1790,
        694,
        "#f3f1f1"
      ]
    }
  ]
}
[/block]
5. Your subscription should be automatically confirmed. Click the refresh icon to make sure the **Subscription ID** is not *PendingConfirmation*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/043c9ef-AWS-CloudWatch-Pending-Confirmation.png",
        "AWS-CloudWatch-Pending-Confirmation.png",
        1600,
        252,
        "#f2f2f2"
      ]
    }
  ]
}
[/block]
6. Go to your EC2 Instances Console.  Select your instance, click **Actions**, select **CloudWatch Monitoring**, and click **Add/Edit Alarms**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3f391ea-CloudWatch-Add-Alarms.png",
        "CloudWatch-Add-Alarms.png",
        1512,
        646,
        "#c1c3c4"
      ]
    }
  ]
}
[/block]
7. Click **Create Alarm**.
8. Select your notification from the dropdown menu, configure the settings that you would like to use for the alarm, and click **Create Alarm**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aa20086-CloudWatch-Create-Alarm.png",
        "CloudWatch-Create-Alarm.png",
        2128,
        1024,
        "#f7f7f8"
      ]
    }
  ]
}
[/block]
9. At this point, you will receive alerts in PagerDuty for when an alarm has reported a critical alert, but the PagerDuty incident will not be resolved when the alarm clears. To enable automatic resolution in PagerDuty when an alarm clears, select your instance, click the **Actions** button, click **CloudWatch Monitoring**, and select **Add/Edit Alarms** again.

10. You will see the alarm that you created earlier. Click **view** under **More Options.** 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/833e008-CloudWatch-Alarm-Details.png",
        "CloudWatch-Alarm-Details.png",
        1396,
        634,
        "#eff1f3"
      ]
    }
  ]
}
[/block]
11. Select your alarm, click the **Actions** button, then click **Modify**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/07c8eea-CloudWatch-Modify.png",
        "CloudWatch-Modify.png",
        1556,
        332,
        "#d8dbde"
      ]
    }
  ]
}
[/block]
12. On the **Modify Alarm** screen, verify your alarm threshold and settings. Add a new **Action** to Send Notification(s) when the alarm state reaches **ALARM**, by clicking **+ Notification**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/73c534a-CloudWatch-Add-Notification.png",
        "CloudWatch-Add-Notification.png",
        1930,
        1574,
        "#f9f9f9"
      ]
    }
  ]
}
[/block]
13. Add a notification for the **OK** state and check that your **ALARM** state notification is correct. Ensure both notifications are being sent to the **Topic** created earlier in the integration. Make sure to save your changes.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf3bbbd-CloudWatch-Actions.png",
        "CloudWatch-Actions.png",
        1918,
        1014,
        "#f7f6f7"
      ]
    }
  ]
}
[/block]
14. You should then see that your Alarm was saved successfully.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe6fdf8-CloudWatch-Alarm-Saved.png",
        "CloudWatch-Alarm-Saved.png",
        1560,
        474,
        "#e8eaea"
      ]
    }
  ]
}
[/block]
15. Congratulations! You have now integrated Amazon CloudWatch with PagerDuty! Now when your alarm threshold is met, an incident will be triggered within PagerDuty.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6604e40-aws-cloudwatch-congrats-step15.png",
        "aws-cloudwatch-congrats-step15.png",
        602,
        383,
        "#f8f8f9"
      ]
    }
  ]
}
[/block]
16. Once that alarm is back in an OK state, the incident will automatically resolve within PagerDuty.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7c17dc9-aws-cloudwatch-final-step16a.png",
        "aws-cloudwatch-final-step16a.png",
        602,
        381,
        "#f7f8f9"
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
        "https://files.readme.io/549af62-AWS-CloudWatch-resolved-PD-incident.png",
        "AWS-CloudWatch-resolved-PD-incident.png",
        2240,
        398,
        "#f0f0f0"
      ]
    }
  ]
}
[/block]
## FAQ

### What alarm statuses affect PagerDuty incidents?

An alarm with status *ALARM* will trigger incidents, and status OK will resolve them. Alarms with status *INSUFFICIENT_DATA* will **only** trigger PagerDuty incidents. If you need *INSUFFICIENT_DATA* to resolve an incident, we recommend using an <a href="https://www.pagerduty.com/docs/guides/email-integration-guide/">email integration</a> instead.

### If I use an email integration, how can I verify my PagerDuty service’s email address?

If you send a confirmation email to your service’s PagerDuty address, you will be able to view the message body and verify that address from the PagerDuty console. To do so, find the incident that is created by the email and view its details to verify the email address.

The link to verify will be in the incident details. The SNS confirmation page requires JavaScript, which can not be executed in the iframe the message is rendered in. To confirm your subscription, open the confirmation link in a new tab or window by right-clicking on the link and choosing **Open Link in New Tab/Window**.

### How can I change how events from CloudWatch are deduplicated into PagerDuty?

Navigate to your PagerDuty Service -> click the **Integrations** tab -> click the wheel cog to the right of your Amazon CloudWatch integration -> click **Edit** -> change the value for the **Correlate events by** option.

### Why are my CloudWatch events not triggering incidents in PagerDuty?

Events that are not sent properly from CloudWatch will be dropped and will not trigger alerts in PagerDuty. This integration expects to find in the `Message` property a nested JSON-encoded object from which meaningful data about the alert can be extracted to compose the PagerDuty incident. You can find details on Amazon's SNS Message attributes here: 

https://docs.aws.amazon.com/sns/latest/dg/sns-message-attributes.html