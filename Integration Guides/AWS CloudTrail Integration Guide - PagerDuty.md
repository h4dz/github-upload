---
title: "AWS CloudTrail Integration Guide | PagerDuty"
excerpt: "Integration Guide for AWS CloudTrail"
---
#Integration Overview

PagerDuty’s integration with AWS CloudTrail enables automated response workflows for activities that could affect compliance and security issues in your AWS ecosystem. PagerDuty provides the opportunity to group alerts alongside other ongoing issues and it has seamless integrations with systems of record like JIRA and SNOW. This is a one-way integration, sending alerts to PagerDuty.

Follow the instructions below to configure AWS CloudTrail with PagerDuty. If you have any questions or need any assistance, please contact our support team at <a href="mailto:support@pagerduty.com">support@pagerduty.com</a>.

# In PagerDuty 

There are two ways that AWS CloudTrail can be integrated with PagerDuty: via Global Event Routing or through an integration on a PagerDuty Service.

##Integrating with Global Event Routing

Integrating with Global Event Routing may be beneficial if you want to build different routing rules based on the payload coming from AWS. If you would like to learn more, please visit our article on [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing). 

1. From the **Configuration** menu, select **Event Rules**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/11d80f2-PHD-Event-Rules.png",
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
        "https://files.readme.io/c15b6c3-PHD-Global-Event-Rules-Key.png",
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

You can now proceed to the [In the AWS Management Console](https://support.pagerduty.com/v1/docs/aws-cloudtrail-integration-guide#section-in-the-aws-management-console) section below. 

##Integrating with a PagerDuty Service

Integrating with a PagerDuty Service directly can be beneficial if you don’t need to route alerts from AWS to different responders based on the event payload. You can still use [service-level event rules](https://support.pagerduty.com/docs/event-management#section-configure-event-rules-for-a-service) to perform actions such as suppressing.

1. From the **Configuration** menu, select **Services**.
2. On your Services page: If you are creating a new service for your integration, click **+Add New Service**. It is recommended that you create a service specifically for AWS CloudTrail notifications.

If you are adding your integration to an existing service, click the name of the service you want to add the integration to. Then click the **Integrations** tab and click the **+New Integration** button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/71c8d62-AWS-CloudTrail-Add-New-Service.png",
        "AWS-CloudTrail-Add-New-Service.png",
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
        "https://files.readme.io/8ab29ac-GuardDuty-New-Integration.png",
        "GuardDuty-New-Integration.png",
        1652,
        200,
        "#f2f8f2"
      ]
    }
  ]
}
[/block]
3. Select AWS CloudTrail from the **Integration Type** menu and enter an **Integration Name**.
If you are creating a new service for your integration, in General Settings, enter a **Name** for your new service. Then, in Incident Settings, specify the **Escalation Policy**, **Notification Urgency**, and **Incident Behavior** for your new service.
4. Click the **Add Service** or** Add Integration** button to save your new integration. You will be redirected to the Integrations page for your service.
5. Copy the **Integration URL** for your new integration.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/80935c2-AWS-CloudTrail-Integration-URL.png",
        "AWS-CloudTrail-Integration-URL.png",
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
        "https://files.readme.io/06d18d5-AWS-CloudTrail-SNS-Create-Topic.png",
        "AWS-CloudTrail-SNS-Create-Topic.png",
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
        "https://files.readme.io/1d5a466-AWS-CloudTrail-Create-Subscription.png",
        "AWS-CloudTrail-Create-Subscription.png",
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
        "https://files.readme.io/b00a9ba-CloudTrail-Create-Subscription.png",
        "CloudTrail-Create-Subscription.png",
        1187,
        696,
        "#f1f0f1"
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
        "https://files.readme.io/0bd4428-AWS-CloudTrail-Pending-Confirmation.png",
        "AWS-CloudTrail-Pending-Confirmation.png",
        1600,
        252,
        "#f2f2f2"
      ]
    }
  ]
}
[/block]
6. Search for **CloudTrail** in your AWS Management Console.
7. Create a **[trail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-a-trail-using-the-console-first-time.html)** if you do not already have one. Note that you can optionally send the trail data to a newly created S3 bucket. 
8. In the **CloudTrail** console, click the trail that you would like to integrate with PagerDuty. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/285e3ff-CloudTrail-Click-Trail.png",
        "CloudTrail-Click-Trail.png",
        2360,
        468,
        "#f3f4f5"
      ]
    }
  ]
}
[/block]
9. If you have not yet configured CloudTrail to deliver logs to CloudWatch logs, start by pressing the **Configure button**. If you have already integrated CloudTrail with CloudWatch Logs, choose a log group name and click **Continue**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2476e9-CloudTrail-Configure-Trail.png",
        "CloudTrail-Configure-Trail.png",
        2424,
        1112,
        "#fafbfb"
      ]
    }
  ]
}
[/block]
10. On the next screen, click the **Allow** button at the bottom right to allow communication between CloudTrail and CloudWatch.
11. After configuring CloudTrail to send data to CloudWatch Logs, navigate to the **CloudWatch** console where you can configure an **Alarm** based on a CloudTrail finding.
12. In the CloudWatch console, click **Logs**, select the radio button to the left of the log group that you would like to set a filter on, then click **Create Metric Filter**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/44e49f9-CloudTrail-Create-Metric-filter.png",
        "CloudTrail-Create-Metric-filter.png",
        1950,
        654,
        "#f4f3f5"
      ]
    }
  ]
}
[/block]
13. Define a [pattern](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/FilterAndPatternSyntax.html) for the type of activity you’d like to send to PagerDuty and click **Assign Metric**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f61d538-CloudTrail-Assign-Metric.png",
        "CloudTrail-Assign-Metric.png",
        2042,
        1398,
        "#f8f8f9"
      ]
    }
  ]
}
[/block]
14. Choose an existing [Metric Namespace](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_concepts.html#Namespace) or create a new one, and name the metric. Then click **Create Filter**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0021098-CloudTrail-Create-Metric-Filter2.png",
        "CloudTrail-Create-Metric-Filter2.png",
        2048,
        830,
        "#f6f5f6"
      ]
    }
  ]
}
[/block]
15. After creating the Filter, click **Create Alarm**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/328b25a-CloudTrail-Create-Alarm.png",
        "CloudTrail-Create-Alarm.png",
        2044,
        810,
        "#f5f7f6"
      ]
    }
  ]
}
[/block]
16. On the **Modify Alarm** screen, verify your alarm threshold and settings. Add a new **Action** to Send Notification(s) when the alarm state reaches **ALARM**, by clicking **+ Notification**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3c0a66f-CloudTrail-Add-Notification.png",
        "CloudTrail-Add-Notification.png",
        2008,
        1536,
        "#f9f9fa"
      ]
    }
  ]
}
[/block]
17. Add a notification for the **OK** state and check that your **ALARM** state notification is correct. You'll want to ensure both notifications are being sent to the **Topic** created earlier in step 2 (above). Click **Create Alarm** to save your changes. You should now see PagerDuty incidents if the alarm thresholds are breached.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dae08a8-CloudTrail-Actions.png",
        "CloudTrail-Actions.png",
        2006,
        974,
        "#f8f7f7"
      ]
    }
  ]
}
[/block]
Congratulations, you have now integrated AWS CloudTrail with PagerDuty! For more information on how to adjust settings to deduplicate events within PagerDuty, please visit our article on [Event Management](https://support.pagerduty.com/docs/event-management).