---
title: "Business Services"
excerpt: ""
---
Business services provide a way to model capabilities that span multiple technical services and that may be owned by several different teams. Mapping [technical services](https://support.pagerduty.com/docs/services-and-integrations#section-configuring-services-and-integrations) to the business services they support lets responders see the business services that an incident could be affecting and, with PagerDuty Visibility, it lets others in the business see when there is an incident affecting one of the business services they care about.

To set up PagerDuty Visibility, the first step is to configure business services. While it is possible to configure multiple levels of business service dependencies, note that only the top level business services will appear in the Visibility dashboard. Once your business services are properly configured, you should see them on the Visibility dashboard in your mobile app.

PagerDuty Visibility lets others in the business see when there is an incident affecting one of the business services they care about. Enterprise plans and ones with [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) can also have stakeholders automatically notified when a business service is disrupted.


---

##Creating Business Services
Ideally, business services are:
* Recognizable to non-technical stakeholders
* Supported by 1 or more technical services in PagerDuty
* Can have clearly defined impact metrics that are meaningful to non-technical services

You may have business services listed on an external status page, within a service catalog/CMDB, or defined in relation to existing health metrics from a monitoring tool.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/339d8cb-business-services-edit-menu.png",
        "business-services-edit-menu.png",
        1434,
        705,
        "#ebeced"
      ],
      "caption": ""
    }
  ]
}
[/block]
1. Go to **Configuration** and select **Business Services**.
2. Click **Create New Business Service**. 
3. Enter a meaningful name that will define the business service and provide a description.
4. Enter the owner as yourself or a point of contact for the business service. *(Optional)*
5. If you are on an **Enterprise** plan or one with our [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) package, select an existing [response play](https://support.pagerduty.com/docs/response-automation) that will automatically notify responders and stakeholders if the [business service becomes disrupted](#section-analyzing-disrupted-business-services). *(Optional)*
6. Under **Services this business service depends on**, add any applicable service that would impact this business service.
7. Under **Services relying on this business service**, apply any *(preferably business)*  services that this service would depend on.
8. Select **Save Changes to this Service** to create the service. 
[block:callout]
{
  "type": "warning",
  "body": "Sometimes there is a technical service that supports a business service but that is not critical to its function. You may prefer to omit **non-critical technical services** that support a business service, since a disruption to one of those technical services does not necessarily mean that the business service is disrupted."
}
[/block]
## Viewing Business Services within the Visibility Mobile Dashboard


[block:callout]
{
  "type": "info",
  "body": "The Visibility Mobile Dashboard is a feature within our [PagerDuty Visibility](https://support.pagerduty.com/v1/docs/pagerduty-visibility) product. It is included in our Enterprise plan. For other plans, it is a new subscription available on top of your existing PagerDuty account. Please [contact our Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with this feature suite."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [],
      "caption": ""
    }
  ]
}
[/block]
Top-level business services are able to be viewed within the Visibility mobile dashboard. To access, navigate to **☰ > Visibility**.
Here you will be able to view a top-level view of any disrupted business services and all healthy business services.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ce1557-Mobile_intro_1.jpg",
        "Mobile_intro_1.jpg",
        852,
        1733,
        "#1c2733"
      ],
      "caption": ""
    }
  ]
}
[/block]
 ### Analyzing Disrupted Business Services
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d4bc626-Mobile_intro_2.jpg",
        "Mobile_intro_2.jpg",
        852,
        1733,
        "#202b37"
      ],
      "caption": ""
    }
  ]
}
[/block]
A business service is disrupted when an incident with a priority is triggered on a technical service connected to the business service, and the business service was not already in a disrupted state due to another incident. 

Selecting a business service will display the detailed view:

  * Name and description of the business service
  * Point of contact (if entered)
  * [Impact Metrics](doc:impact-metrics) for the business service
  * Supporting technical services

If the business service is disrupted, additional details are included:
* Priority and duration of the disrupting incident
* Timeline of any status updates *through Modern Incident Response*
* The technical services list will indicate the disrupted technical service(s)