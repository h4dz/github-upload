---
title: "Bitbucket Integration Guide | PagerDuty"
excerpt: "Integration Guide for Bitbucket"
---
Bitbucket is the Git solution for professional teams. Bitbucket core features include pull requests, branch permissions and inline comments. With the Bitbucket integration for PagerDuty, you can notify on-call engineers about failures within your Bitbucket pipelines.

**Note:** this integration is intended for Bitbucket cloud.

#PagerDuty Configuration
Within your PagerDuty account, a Custom Event Transformer needs to be created. This allows PagerDuty to process webhooks from your Bitbucket account. Each repository in Bitbucket can send failure information to different PagerDuty Services. Determine which Bitbucket repository and PagerDuty service you would like to integrate.

1. Go to **Configuration** :fa-arrow-right: **Services**. 
2. Select the PagerDuty service you wish to integrate with, then go to the **Integration** tab
3. Press **New Integration**. You will be taken to the **Add an Integration** screen.
4. Provide a title for the integration, such as "Bitbucket". From the **Integration Type** drop down, search for **Atlassian Bitbucket Pipelines**, then press **Add Integration**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4390ffd-bitbucket-pagerduty-integration.png",
        "bitbucket-pagerduty-integration.png",
        2070,
        998,
        "#dcdfdf"
      ]
    }
  ]
}
[/block]
5. You will be taken back to the Integrations tab showing the newly added integration. Click the name of the **Atlassian Bitbucket Pipelines** integration you created above.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46c64da-bitbucket-integration.png",
        "bitbucket-integration.png",
        2428,
        1262,
        "#e4e6e8"
      ]
    }
  ]
}
[/block]
6. From this screen, highlight and copy the **Integration URL** value. This will be needed when you configure webhooks in your Bitbucket account. 



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8af2c0b-bitbucket-integration-pd.png",
        "bitbucket-integration-pd.png",
        2440,
        566,
        "#d3d5d7"
      ]
    }
  ]
}
[/block]
#Bitbucket Configuration
The remaining configuration resides on the Bitbucket side, through the Bitbucket user interface. You will be adding webhooks that will send failure information to PagerDuty.

1. Open the repository you want to integrate with PagerDuty. From the left side navigation, open **Settings**.
2. Click **Webhooks** from the Workflow sub-heading, followed by **Add Webhook**.
3. Provide a title, then paste the PagerDuty URL you copied from the above steps.
4. Change the **Triggers** radio option to **Choose from a full list of triggers**.
5. Under **Repository**, select **Build status updated**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c67bbf0-Screen_Shot_2018-09-01_at_3.01.13_PM.png",
        "Screen Shot 2018-09-01 at 3.01.13 PM.png",
        1108,
        904,
        "#f8f8f8"
      ]
    }
  ]
}
[/block]
6. **Save** the configuration. 

You have successfully completed setting up the integration. When there is a failure in your pipelines, a PagerDuty incident will notify on-call responders. When the failure recovers, a SUCCESSFUL message is sent to PagerDuty and the PagerDuty incident will be automatically resolved.