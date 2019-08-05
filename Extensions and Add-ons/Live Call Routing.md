---
title: "Live Call Routing"
excerpt: ""
---
Live Call Routing allows you to expand your customer support by directing phone calls and voicemails to on-call responders. Please note that this guide will only be relevant after a PagerDuty employee has enabled Live Call Routing on your account.
[block:callout]
{
  "type": "info",
  "body": "Live Call Routing is available as an add-on to customers on the Platform Team and Platform Business plans, and included in Enterprise plans. Please [contact our Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with this feature."
}
[/block]
##Add a Live Call Routing number
1. Go to **Add-ons → Live Call Routing**.
2. Click **New Routing Number**.
3. Select the country where you'd like the number to be based (and the area code, optionally, if available).
4. Click **Continue**.
5. Enter a name for the routing number.
6. Choose how you'd like calls to connect, [Leave a Message or Connect Directly](https://support.pagerduty.com/v1/docs/live-call-routing#section-choosing-a-connection-type).
7. Enter some descriptive text to be read to the caller.
8. Select an associated service (this is where incidents will trigger).
9. Click **Update Routing Number**.

To add additional Live Call Routing lines, or to request a toll free Live Call Routing number, please [reach out to our Sales Team](https://www.pagerduty.com/contact-sales/).

##Tying multiple services to a Live Call Routing number
You can associate up to 9 services with a single Live Call Routing number and set up a phone tree-like structure. When dialing in, an automated voice will announce, "Press 1 for Nagios Critical. Press 2 for Datadog Alerts... etc." Depending on the caller's selection, after a brief moment they'll be connected with the appropriate response team.

To change the order, in which services are announced (most critical first, for instance), you can rearrange the list of services on a routing number's **Edit** screen.

###Preventing Live Call Routing from Reading Your Services' Names
By default, Live Call Routing will attempt to read your services' name to the caller so they can be connected to the correct escalation policy. If your services reference internal jargon, this information may not make sense to the caller.

You can configure Live Call Routing to only play the greeting, and not read out services' names. Please note that if you select this option, you'll need to update the greeting with more caller-friendly information.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6a2a264-Screen_Shot_2018-03-12_at_2.51.46_PM.png",
        "Screen Shot 2018-03-12 at 2.51.46 PM.png",
        798,
        487,
        "#f5f1f1"
      ]
    }
  ]
}
[/block]
##Choosing a Connection Type
You can configure Live Call Routing to either leave a message for or connect directly with the on-call responder. The following information is meant to help you understand how each option behaves.

###Leave a Message
- This setting triggers an incident after the caller leaves a message
- The caller's message is attached to a new triggered incident, which is assigned to the on-call responder on the first level of the escalation policy. If more than one person is on-call, PagerDuty will assign the incident to all responders on the **first escalation rule**.
- The incident will then escalate according to the service's escalation policy.

###Connect Directly
- PagerDuty will attempt to connect the caller with the on-call responder on the first level of the escalation policy. 
- You can configure how long each responder has to answer the call before it will escalate to the next responder. The default is 20 seconds.
- If more than one responder is on-call, PagerDuty will randomly cycle through all responders on an escalation level. 
- If a responder has more than one phone number on their user profile, PagerDuty will call them at the first number listed on their Contact Information tab.
- PagerDuty creates an **acknowledged** incident when someone picks up, and **resolves** the incident when the call ends.
- If the responder does not answer the call, PagerDuty will attempt to contact on-call responders at each remaining level of the escalation policy until someone answers. Please note that **PagerDuty will not attempt to call the first level responders again**. Even if the escalation policy is configured to repeat one or more times, it will only go through the escalation policy **one time**.
- If still no one answers, the caller will be prompted to leave a message. An incident will trigger, with the incident description containing the inbound caller ID, and it will be assigned to the on-call responder on the first level of the escalation policy.
- The incident will then escalate as expected according to the service's escalation policy.

##Showing the Live Call Routing Number on Your Phone's Display
For calls that connect directly with responders, you can select an option to show the Live Call Routing number, instead of the caller's number, when a call is received. This can be helpful to add to a contacts list, for example, so it is clear when a call is related to PagerDuty and Live Call Routing.
[block:callout]
{
  "type": "warning",
  "body": "This feature is currently only available for US- and Canada-based Live Call Routing numbers."
}
[/block]
##Listening to a Voicemail
To listen to a voicemail appended to an incident, you will need to navigate to either the incidents page or view the incident itself, you will need to click the **show details** link to expand the incident's details. Click the Listen to Recording link and you will be able to listen to the voicemail.

To listen to the voicemail from the mobile app, tap the incident to view the incident details. Then, tap the **Listen to Recording** link.

##Supported Countries (regular phone numbers)
A Live Call Routing number can be configured for the following countries (subject to availability):

- Australia
- Belgium
- Brazil
- Canada
- Czechia (Czech Republic) `*`
- Finland `*`
- France `*`
- Japan `*`
- India `*`
- Indonesia `*`
- Ireland (Republic of) `*`
- Israel
- Netherlands `*`
- New Zealand
- Singapore `*`
- South Africa  `*`
- Spain `*`
- Sweden `*`
- Puerto Rico (U.S.) `*`
- United Kingdom of Great Britain and Northern Ireland
- United States

`*` *Please reach out to [PagerDuty Support](https://www.pagerduty.com/support/) to request a phone number in these countries*

##Supported Countries (toll-free numbers)
A *toll-free* Live Call Routing number can be configured for the following countries (subject to availability). 
- Australia
- Canada
- India `*`
- Japan `*`
- Netherlands `*`
- Singapore `*`
- Sweden `*`
- United Kingdom of Great Britain and Northern Ireland
- United States

`*` *Please reach out to [PagerDuty Support](https://www.pagerduty.com/support/) to request a phone number in these countries*
[block:callout]
{
  "type": "info",
  "body": "While the list above represents countries where we can create an inbound Live Call Routing number, responders can *receive* Live Call Routing-generated calls in any [supported country](doc:supported-countries).",
  "title": ""
}
[/block]
##Troubleshooting

###"You have reached a PagerDuty Live Call Routing line that is not set up yet; please call back later" 
If you hear this message when calling your Live Call Routing number, here are some things you should check:

1. Is your Live Call Routing instance associated with at least one service?
2. Are the service(s) using your Live Call Routing instance [disabled or in a maintenance window](doc:maintenance-windows)?
3. Is anyone on call for this service? Note that [no incident can trigger if no one is on call](https://support.pagerduty.com/docs/why-incidents-fail-to-trigger#section-nobody-was-on-call).
4. Do the on-call responders in the service's escalation policy have a phone contact method listed in the [Contact Information](doc:configuring-a-user-profile#section-contact-information) section of their user profile? Note that **Live Call Routing will not check the SMS field**, so on-call responders must have a number listed in the **Phone** field of their contact information in order for it to work.