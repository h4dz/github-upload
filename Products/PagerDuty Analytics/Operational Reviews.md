---
title: "Operational Reviews"
excerpt: ""
---
The Operational Reviews feature offers metrics for three different types of reviews, targeted at different levels of leadership in a digital business. Each review type contains scorecards intended to help drive operational review meetings. 

- [Team On-Call Handoff Reviews](/docs/operational-reviews#section-team-on-call-handoff-reviews)
- [Service Performance Reviews](/docs/operational-reviews#section-service-performance-reviews)
- [Business Outcomes Reviews](/docs/operational-reviews#section-business-outcomes-reviews)
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Operational Reviews is a feature of the [PagerDuty Analytics](https://support.pagerduty.com/docs/pagerduty-analytics) add-on product designed to work with the PagerDuty platform. Please [contact our Sales team](https://www.pagerduty.com/contact-sales/) for information on adding PagerDuty Analytics to your subscription."
}
[/block]
##Foundational Concepts

Each scorecard incorporates Interruptions and Major Incidents.

###Interruptions
Interruptions are when an on-call responder is notified by SMS (text), mobile push notification or phone call and, within our metrics, are a unique count of notifications that an incident sends out. The same type of notification sent from various channels (SMS, phone call, push) to the same destination are counted as one interruption. Email notifications are excluded, as email is not considered an interrupting channel.

###Major Incidents

A major incident is defined as any incident that requires a coordinated response, often across multiple teams. They are typically highly noticeable by customers, so fixing the problem is of the greatest importance. Major incidents are often referred to as [P1, P2](https://support.pagerduty.com/docs/incident-priority), or SEV-1, SEV-2 in most organizations. In PagerDuty Analytics, they are defined as the top two levels of your priority settings, or if [multiple responders are added](https://support.pagerduty.com/docs/mobilizing-a-response#section-add-responders) and acknowledge. In the Quarterly Business Outcomes scorecard, these designations are listed on the upper left hand side in pills that can say P1, P2, SEV-1, SEV-2 or MRI for Multiple Responders Involved.

##Team On-call Handoff Reviews

Team On-Call Handoff Reviews can help on-call teams capture and improve on alert fatigue and responder well-being. The metrics focus on [interruptions](/docs/operational-reviews#section-interruptions) to responders during business hours, off hours and sleep hours, MTTA/MTTR, escalations, and the most frequent incidents.

###Metrics
[block:parameters]
{
  "data": {
    "0-0": "**Individual Vibe**",
    "1-0": "**Business hours interruptions**",
    "1-1": "The count of interrupting notifications sent between 8am and 6pm, in the user's local time.",
    "0-1": "**Sad face** - Given that a user has one or more sleep-hours interruptions, two or more off-hours interruption or more than five total interruptions in the past week, the user gets a Sad face.\n**Meh face** - Given that a user has one off-hours interruption, and five or less business-hours interruptions, the user gets a Meh face.\n**Happy face** - Given that a user has no off-hours, no sleep-hour interruptions and less than five business-hours interruptions, the user gets a Happy face.",
    "2-0": "**Total Off-hours interruptions**",
    "3-0": "**Total Sleep hours interruptions**",
    "4-0": "**Hours interrupted per day**",
    "5-0": "**Loudest Service**",
    "6-0": "**Most Frequent Incidents**",
    "7-0": "**Interruptions per service**",
    "8-0": "**Total off-hours interruptions**",
    "9-0": "**Escalations**",
    "10-0": "**Major Incidents**",
    "2-1": "The count of interrupting notifications sent between 6pm and 10pm Monday to Friday or during 8am to 10pm over the weekend, in the user's local time.",
    "3-1": "The count of interrupting notifications sent between 10pm and 8am, in the user's local time.",
    "4-1": "The number of hours in a day where a user receives one or more interrupting notifications. The max is 24 per day.",
    "5-1": "The service that sends out the highest number of unique interrupting notifications.",
    "6-1": "An aggregation of the most common incident's descriptions",
    "7-1": "A breakdown of interruptions per service, displayed in a pie chart.",
    "8-1": "Total count of off-hours interruptions for the team members in the team/teams in the weekly report.",
    "9-1": "Total count of escalations which occurred in the team/teams' weekly report, including both manual and time-out escalations.",
    "10-1": "The count of major incidents which occurred on the technical services supported by the team or teams in the weekly report.",
    "11-0": "**Company Averages This Period**",
    "11-1": "The company average shows the average interruption summary among incident responders for a specified time period. We take all individuals who were interrupted at least once, use their timezones to determine when interruptions took place, and and divide the totals by the total number of interrupted individuals for the time period. We then use this data and surface comparisons on the team individual level to highlight whether any individual member experienced below or above average operational load relative to the rest of their peers"
  },
  "cols": 2,
  "rows": 12
}
[/block]
##Service Performance Reviews

These reviews are designed to help guide smart investments into service performance. The metrics focus on aggregate measurements such as time without major incidents, MTTR for major and high urgency incidents, and details breakdown of the incidents and services that may be worth the most attention and investment. 

###Metrics
[block:parameters]
{
  "data": {
    "0-0": "**Time Without Major Incidents**",
    "1-0": "**Time Without High-urgency Incidents**",
    "2-0": "**Worst Performing Technical Services**",
    "3-0": "**Business Service At Risk**",
    "0-1": "Per the definition of Major Incident, calculates the net duration of major incidents in a month (removing any overlapping time) and calculates the percentage of time without major incidents.",
    "1-1": "Calculates the net duration of high-urgency incidents in a month (removing any overlapping time) and calculates the percentage of time without high-urgency incidents.",
    "2-1": "Services with the largest number of incidents. Incident count includes both High and Low-Urgency. Business Service affiliations and Team associations that the technical service may have will also appear here.",
    "3-1": "There are two ways of calculating the business service at risk:\n\n* One is to identify the business service with the longest single major incident. This is calculated by adding up the overlapping total major incident durations on the technical services that support a business service (i.e. flattening the time).\n\n* The second is to identify the business service with the highest major incident volume. This is calculated by adding up the major incident count on the technical services that support a business service."
  },
  "cols": 2,
  "rows": 4
}
[/block]
##Business Outcomes Reviews

[Business Outcomes Reviews](doc:business-services) will help business and technology leaders gain insight into how service operations affect business outcomes. The metrics focus on the cost to the company to operate services (hours lost responding, cost of responder time), the impact on customers (aggregate major incidents duration), and a summary of the high impacting incident from the quarter. 

###Metrics
[block:parameters]
{
  "data": {
    "0-0": "**Time Without Major Incidents**",
    "1-0": "**Responder Cost in Hours**",
    "2-0": "**Estimated Response Cost**",
    "3-0": "**Time in Response (per team)**",
    "4-0": "**Business Service At Risk**",
    "0-1": "Per the definition of Major Incident, calculates the net duration of major incidents in a month (removing any overlapping time) and calculates the percentage of time without major incidents.",
    "1-1": "The cumulative labour hours (i.e. from each engaged responder's time to acknowledge to the end of an incident) spent on major incidents.",
    "2-1": "The cost in hours multiplied by an estimated hourly labour cost, which is, conservatively, $50.",
    "3-1": "The percentage of cost in hours over total available labour hours on a team, assuming 40 hours/week/team member.",
    "4-1": "There are two ways of calculating the business service at risk:\n\n* One is to identify the business service with the longest single major incident. This is calculated by adding up the overlapping total major incident durations on the technical services that support a business service (i.e. flattening the time).\n\n* The second is to identify the business service with the highest major incident volume. This is calculated by adding up the major incident count on the technical services that support a business service.",
    "5-0": "**Most Time in Response**",
    "5-1": "The top 3 teams that were affected by major incidents within the period along with the number of major incidents, cost in hours, and the percentage of time spent on unplanned effort that the incidents had caused."
  },
  "cols": 2,
  "rows": 6
}
[/block]