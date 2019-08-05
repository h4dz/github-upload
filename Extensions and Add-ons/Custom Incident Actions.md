---
title: "Custom Incident Actions"
excerpt: ""
---
Custom incident actions provide a user assigned to an incident with a quick way to execute custom logic housed outside of the PagerDuty system. Customers can host their own custom scripts that execute when these actions are executed, which provides users with a nearly limitless number of possible actions.

##Creating a Custom Incident Action
To create a custom incident action, select **Extensions** within the **Configuration** drop-down menu in the navigation bar. Then, click **+ New Extension** in the **Service Extensions tab** and search for ‘Custom Incident Action’, as the **Extension Type**. 

From here you will be taken to the **Custom Incident Action** extension page. If you have not yet created any custom actions, the page will display a message with information about custom incident actions. On this page, select **New Action** to create your new action.

You will be brought to a form where you can configure your custom action. The most important field is the endpoint URL, which is where we will be sending the HTTP POST requests when your custom action button is selected. When you have finished configuring your custom action, you can select **Create Action** to finish creating your action.

For more information about the payload you will receive through a PagerDuty webhook, please [visit this page](https://v2.developer.pagerduty.com/docs/webhooks-v2-overview). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af04abd-custom-incident-actions-2.png",
        "custom-incident-actions-2.png",
        1138,
        1058,
        "#ececec"
      ]
    }
  ]
}
[/block]
Once you have created your custom action, you will see the action button available on all incidents on that service.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/144d149-custom-incident-actions-3.png",
        "custom-incident-actions-3.png",
        526,
        722,
        "#ebf0eb"
      ]
    }
  ]
}
[/block]
When a user clicks on this button, it will fire an HTTP POST request with data on the incident to the endpoint URL specified during configuration. You can then build a script that listens for this request and executes custom logic when a request is received.

##Common Use Cases
###Restart Server
Create a **Restart Server** button on your incidents that, when selected, restarts the server associated with the incident. The custom action POST request will include details on the incident that would allow a single script to dynamically determine the server in need of a restart.

###Add Diagnostics
Create an **Add Diagnostics** button that fetches diagnostic data on the affected infrastructure and appends the data as a note on your PagerDuty incident. This gives your users visibility into key infrastructure data right in the PagerDuty incident.

###Revert Last Commit
Create a **Revert Last Commit** button that will revert the last commit in your repository that houses the source code for the affected service. This allows your users to quickly roll-back a bad deploy without leaving the PagerDuty platform.

###Update Status Page
Create an **Update Status Page** button that will let your users update your status page with one click. This lets your users update your customers as soon as an incident occurs.