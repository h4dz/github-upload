---
title: "ServiceNow Troubleshooting Guide"
excerpt: ""
---
Below are some common questions and troubleshooting steps for the ServiceNow integration.

# When is an incident sent to PagerDuty?

By default, the PagerDuty application triggers a PagerDuty incident if the assignment group has been tied to a PagerDuty service and if the incident is either a P1 or P2. This can be customized.

# I'm not seeing any updates in PagerDuty from ServiceNow.

Check that the PagerDuty service webhook URL is correct. It should look similar to `https://subdomain.service-now.com/x_pd_integration_pagerduty2sn.do?webhook_key=key1`.

Check that the group in ServiceNow has both the service and escalation policy ID. You may need to add the two PagerDuty fields to the group form.

Next, check to see if the webhook messages have been saved in ServiceNow. In ServiceNow, go to **PagerDuty &#9658; Imports &#9658; Webhook Import Rows** and look for records with creation time that coincides with the time that the incident in PagerDuty was triggered, acknowledged or resolved.

# I've checked the webhook and import rows and it looks good, but my incidents in ServiceNow are not automatically resolving.

Check to see if you have any custom choices set up for the *State* field in the ServiceNow incidents model:

1. Right click on the label of the *State* field (i.e. that would say "New" or "Resolved"), 
2. Select **Configure Dictionary**
3. Switch to **Advanced view**
4. Go to the **Choices** tab and look for entries with higher numbers in the **Value** field.

The integration follows the same convention as the out-of-box state values of ServiceNow. That is to say, higher numbers imply a more advanced state (i.e. a 6 or higher would be done/resolved or some variant thereof). Hence, if the state of the incident that did not automatically resolve is of a higher numeric value, but the incident did not resolve, it is because it was treated as already resolved.

To correct this, you will need to modify the custom choice values that you have configured for the **State** field to be lower than 6, so that they are treated as an unresolved state (if they reflect that).

# Some actions are not updated in ServiceNow from PagerDuty.

Check the user's email address in ServiceNow to make sure it matches the user's email address in PagerDuty.

#How do I customize the integration?
Business rules determine when to update PagerDuty from actions that occur in ServiceNow. They can be found by going to **PagerDuty** in the left-hand menu, clicking Configuration files, and going to the **Business Rules** tab. You can now select a business rule and view it's filter conditions.

The majority of the JavaScript used for the application is able to be modified and can be found in the **PagerDuty** menu item, clicking **Configuration files**, and going to **Script Includes**. The scripts consist of:
- The **PagerDuty** script contains methods used to trigger, reassign and resolve incidents along with other helper methods. The `triggerIncident` method would be where a customer who wants to include more data in incidents in PagerDuty from ServiceNow would make modifications.
- **PagerDutyInbound** contains methods used for processing incoming webhook data.
- **PagerDutyProvisioning** is used to create users, escalation policies and services within PagerDuty.
- **PagerDuty_REST** is the only script that cannot be modified. It contains basic methods to perform GET, POST and PUT calls to the PagerDuty API.

Webhooks can also be customized in the **Webhook Import Service** web service, including the **PagerDuty Webhook Import** transform map.

#How can I make the PagerDuty fields visible in ServiceNow?
At this time, there are 2 fields for PagerDuty on the group form, 2 fields on the incident form and 1 field on a user form. The process to make each one visible is the same: When viewing the form you want to change, right click the grey header, select **Configure** and click **Form Layout**. The new page will have two columns. Look for the PagerDuty field(s) you want in the left column, select it and click the right arrow to add it. Save once complete. Go back to the form and you should see the new field(s) added.

#How can I manually edit the PagerDuty fields?
Right click on the field label, click **Configure Dictionary**, then uncheck **Read only** on the new page and save.

#Can I/how do I connect more than one PagerDuty service to a ServiceNow group?
That's not possible at the moment. The mapping is 1-to-1.

#I thought I installed the PagerDuty app, but I can't find it in the left-hand navigation menu.
If you just installed the app, try a hard refresh in your browser, or log out and back in again, as the left menu may just not have been reloaded after the install process. This is the most common issue.

Make sure the PagerDuty app has been added to your current instance from the ServiceNow store (store.servicenow.com).

Install the app to your current instance by going to System Applications, selecting Applications, and clicking the Downloads tab.

#I did all the above, but I still can't see the app. What now?
Check to see if you have any plugins that could prevent the installation from succeeding. We've seen one instance where a customer had a plugin installed that tried to encrypt each attachment within ServiceNow, which lead to the install process of the PagerDuty app looking like it succeeded but in reality it failed, so they couldn't find PagerDuty in the left-hand navigation menu.

#Why aren't incident notes entered in PagerDuty showing up on the ServiceNow incident?
Note synchronization does not happen in real time but is handled whenever the incident record in ServiceNow is updated, or manually initiated by selecting **Refresh PagerDuty Notes** from the context menu in the ServiceNow incident header bar.

If you just upgraded to 3.1 from an earlier version, you will need to enable business rules so that note import can work properly. More info is available in the [ServiceNow integration guide](https://www.pagerduty.com/docs/guides/servicenow-integration-guide/).