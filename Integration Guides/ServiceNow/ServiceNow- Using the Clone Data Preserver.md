---
title: "ServiceNow: Using the Clone Data Preserver"
excerpt: ""
---
In some cases, you may want to clone your ServiceNow production data to a new dev instance. While there can be many motivations for doing so, problems with the PagerDuty integration can occur if the data is cloned without using a Clone Data Preserver. In this article we'll discuss how to avoid common issues that come with replicating an environment in ServiceNow.

## What is the Clone Data Preserver? 
The Clone Data Preserver is a feature within ServiceNow that you can use to define what data should **not** be replaced when cloning one environment into another. 

## Why should I use this?
When you clone your environment, you also clone the PagerDuty integration. When this happens you lose PagerDuty configuration in the target destination, such as the CI or AG mappings, service IDs, and API keys. To clone the PagerDuty integration and have it remain in a functional state, you'll need to utilize the Clone Data Preserver to preserve certain PagerDuty fields beforehand. In the walkthrough below, we'll be creating the Clone Data Preservers in our Production environment, prior to cloning anything to our Dev instance.
[block:callout]
{
  "type": "info",
  "title": "Required Permissions",
  "body": "Please keep in mind that in order to use the Clone Data Preserver feature, your ServiceNow role must include `clone_admin` or `admin`"
}
[/block]

[block:api-header]
{
  "title": "Creating the Clone Data Preservers Manually"
}
[/block]
To begin, navigate to System Clone :fa-arrow-right: Preserve Data, and select New. We'll begin by addressing the PagerDuty fields in the sys_properties table. In total, we will make 4 separate Clone Data Preservers.
Once you've created a new record for the Clone Data Preserver, select the **sys_properties** table, as shown in the below screenshot. Try to make the name of the Clone Data Preserver as descriptive as possible for your own reference later.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/903b701-Clone_Data_Preserver.png",
        "Clone_Data_Preserver.png",
        2162,
        632,
        "#f3f3f4"
      ]
    }
  ]
}
[/block]
 From here, we're going to be creating **AND** conditions for the following Names. 

- **Name Is** x_pd_integration.default_user
- **Name Is** x_pd_integration.instance_url
- **Name Is** x_pd_integration.sn2pd_mapping
- **Name Is** x_pd_integration.default_service
- **Name Is** x_pd_integration.api_key
- **Name Is** x_pd_integration.webhook_restapi
- **Name Is** x_pd_integration.sn_auth_user
- **Name Is** x_pd_integration.sn_auth_userpwd


Go ahead and save your changes. Once this Clone Data Preserver is created, we'll **create another for the `sys_user` table.** 

Navigate to **System Clone :fa-arrow-right: Preserve Data**, and select **New**.  Select `sys_user` as your table, and add the following condition and save your changes:

- **Name Is** x_pd_integration_pagerduty_id

**Create a new Clone Data Preserver for the `sys_user_group` table with the following conditions:**

- **Name Is** x_pd_integration_pagerduty_webhook
- **Name Is** x_pd_integration_pagerduty_escalation
- **Name Is** x_pd_integration_pagerduty_service
- **Name Is** x_pd_integration_pagerduty_schedule – [v5 only](https://community.pagerduty.com/t/whats-new-servicenow-v5-integration/2160)
- **Name Is** x_pd_integration_pagerduty_team – [v5 only](https://community.pagerduty.com/t/whats-new-servicenow-v5-integration/2160)

**Lastly, create a new Clone Data Preserver for the `cmdb_ci ` table with the following conditions:** 

- **Name Is** x_pd_integration_pagerduty_webhook
- **Name Is** x_pd_integration_pagerduty_service
[block:api-header]
{
  "title": "Creating the Clone Data Preservers by Importing an Update Set"
}
[/block]
As an alternative to creating the Clone Data Preservers manually, you can import one of the following update sets to the origin ServiceNow instance. In keeping with our prod to dev example, you would import the appropriate update set onto your prod instance before cloning over to your new dev instance.


If you're using any iteration of V4, use [this Update Set](https://github.com/PagerDuty/servicenow-updatesets/blob/master/PagerDutyCDP-V4.xml)

If you're using V5, use [this Update Set](https://github.com/PagerDuty/servicenow-updatesets/blob/master/PagerDutyCDP-V5.xml) instead.