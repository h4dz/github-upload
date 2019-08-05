---
title: "Slack V2 Integration Guide"
excerpt: ""
---
The Slack V2 integration, like the [V1 integration](https://www.pagerduty.com/docs/guides/slack-integration-guide/), allows you to action upon PagerDuty incidents within Slack. The V2 update provides new incident response capabilities, with the options to [trigger](https://support.pagerduty.com/docs/incidents#section-triggering-an-incident-with-web-ui-email-or-api), [escalate](https://support.pagerduty.com/docs/reassigning-and-delegating-incidents#section-reassign-or-delegate-an-incident) incidents, run [response plays](https://support.pagerduty.com/docs/response-automation) from Slack and create on-demand Slack channels for collaboration. It also has improvements such as an updated notification design with more context from monitoring tools and actions that respect PagerDuty [user permissions](https://support.pagerduty.com/docs/user-roles). 
[block:callout]
{
  "type": "info",
  "body": "The Slack V2 integration is currently in Early Access; please contact our [Support team](mailto:support@pagerduty.com) or your account representative if you are interested in using it during this phase.",
  "title": "Note"
}
[/block]
##Early Access Notes
- While this feature is in Early Access, users may encounter bugs as we continue to add new capabilities the integration.
- We recommend that you pick a subset of your services to integrate with Slack V2. You can use the V1 and V2 integrations in parallel, but you may see duplicate notifications.
- If you do choose to use Slack V1 and Slack V2 at the same time, you must be using the same Slack Workspace for both integrations. 
[block:api-header]
{
  "title": "Integration Walkthrough"
}
[/block]
##In PagerDuty

1. In the **Configuration** menu, select **Services**.
2. Select the **service** you where you would like to add the extension and click the **Integrations** tab.
3. Under the Extensions section, click **+ New Extension**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4c8420d-slackv2-new-extension.png",
        "slackv2-new-extension.png",
        1674,
        776,
        "#f4f6f4"
      ]
    }
  ]
}
[/block]
4. In the Extension Type section, select **Slack V2 (Early Access)** from the dropdown menu. 
5. Enter a friendly **Name** for the integration, such as `SlackV2-Service-Name` (e.g. If your service name is Shopping Cart, the extension name would be `SlackV2-Shopping-Cart`).  
6. In the Details section you can select which updates you want sent to Slack V2: **Escalate**, **Resolves**, **Acknowledgements** or **Notes** actions. Click **Authorize** to continue.
7. On the authorization screen, ensure that you are in the correct Slack **Workspace**. Please note that if you plan to use Slack V1 and V2 at the same time, you will need to integrate Slack V2 into the same Workspace. Next, select the **channel** where you would like PagerDuty to send messages, then click **Authorize**.

**Note**:
* The Slack V2 integration has new authorization permissions denoted by red alert symbols:

>**Access your workspace’s profile information**: This allows Slack V2 to access your team’s profile information and it is used for Slack user association. The list of members from the channel endpoint only gives PagerDuty your Slack ID and this allows it to obtain necessary usernames.
>**Send messages as you**: This is used to post notifications into the selected channel when a PagerDuty incident has been triggered, updated or resolved.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aad35a8-slackv2-authorization-screen.png",
        "slackv2-authorization-screen.png",
        980,
        1232,
        "#f9f7f7"
      ]
    }
  ]
}
[/block]
8. You will see a message in your Slackbot channel that a new PagerDuty integration has been added to your Slack channel. Click **link your accounts**—this is now required with Slack V2. You will be directed to a PagerDuty screen where you will see a confirmation that your Slack user has been linked to your PagerDuty account, with the option to open your PagerDuty dashboard. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/badf1cd-slackv2-link-accounts.png",
        "slackv2-link-accounts.png",
        1242,
        212,
        "#eff0ef"
      ]
    }
  ]
}
[/block]
9. In Slack you will also see a message in the integrated Slack channel that the PagerDuty integration has been added. If you set up the integration on a private channel, add **@pagerduty_slack_bot** to your channel. 
10. The slash commands for the actions within PagerDuty are `/pduty trigger` and `/pduty help`. When an incident is triggered, the trigger message in Slack will show an **Acknowledge** button, a **Resolve** button, and under the **More actions…** menu you will see the options to **View Details**, **Add a Note**, **Escalate** or **Run a Play**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b851155-slackv2-incident-actions.png",
        "slackv2-incident-actions.png",
        1162,
        332,
        "#f2f4f3"
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
        "https://files.readme.io/869578b-slackv2-incident-more-actions.png",
        "slackv2-incident-more-actions.png",
        1169,
        339,
        "#f3f4f4"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Available slash commands"
}
[/block]
Once the updated integration is installed, new slash commands are available for users to use. These slash commands can be run from Slack channels that are configured with PagerDuty.

**Available commands**
  * /pd help
  * /pd trigger
  * /pd oncall 
[block:api-header]
{
  "title": "Creating on-demand Slack Channels"
}
[/block]
With the updated Slack integration, PagerDuty users can create on-demand Slack channels right from within PagerDuty. These can be created from the incident details view in the web application. You will have the ability to create new public or private channels or associate an existing channel to an incident.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3cc8387-add_slack_channel.png",
        "add_slack_channel.png",
        1664,
        696,
        "#f0efef"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "FAQ"
}
[/block]
##If I already have the Slack V1 extension installed, can I change the extension type to V2?
No. You will need to add Slack V2 as a new extension, and then you can choose whether you would like to use both at the same time or delete the Slack V1 extension.
##How do I know if I’m using V1 or V2 integration when looking at the Slack notification?
The V1 integration has a dark grey PagerDuty icon. The V2 integration has a new bright green PagerDuty icon and it includes a “More actions…” menu.
##If I don’t connect my PagerDuty and Slack accounts, can I still action notifications in Slack?
No. The Slack V2 integration, unlike V1, requires you to connect so that it can respect PagerDuty [user permissions](https://support.pagerduty.com/docs/user-roles).
##How do I provide feedback, suggestions and/or bugs?
Please [contact our Support team](mailto:support@pagerduty.com). 
##How do I view on-call information in Slack?
This is coming very soon. It will come in the form of a slash command that you can run from within Slack.
##What do I do if I’m seeing a `403_client_error` when running the /pduty trigger command?
You are likely attempting to trigger an incident from a Slack channel that is not connected to PagerDuty. For now, go into a Channel that is mapped to PagerDuty and try triggering an incident again. We are currently working on fixing this issue.