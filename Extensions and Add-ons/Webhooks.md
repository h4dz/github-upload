---
title: "Webhooks"
excerpt: ""
---
Webhooks allow you to receive HTTP callbacks when incidents are triggered and updated. Details about the event are sent to a URL you specify, such as [Slack](https://www.pagerduty.com/docs/guides/slack-integration-guide/), [HipChat](https://www.pagerduty.com/docs/guides/hipchat-extension-guide), or your own [custom PagerDuty webhook processor](https://v2.developer.pagerduty.com/docs/webhooks-overview).
[block:api-header]
{
  "title": "Add a Webhook"
}
[/block]
1. Go to **Configuration → Services**, then click the name of the service you want to add a webhook to.
2. Go to the service's **Integrations** tab.
3. Click **New Extension**.
4. For the **Extension Type** select your webhook type or **Generic V2 Webhook**.
5. Give your webhook a **Name**.
6. Enter your endpoint's **URL** in the **Details** field.
7. Click **Save**.

To test your webhook, click **New Incident** on the service and trigger a test incident. Then check your endpoint for updates. We recommend reviewing the webhook PagerDuty sends when an incident triggers. You can do this by using a tool online such as [Beeceptor](https://beeceptor.com/), [webhook.site](https://webhook.site), or [postb.in](https://postb.in/).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f416fdb-webhook.png",
        "webhook.png",
        2104,
        1488,
        "#f5f6f6"
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
        "https://files.readme.io/d5750c0-webhooks5.png",
        "webhooks5.png",
        924,
        255,
        "#393a3c"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "HTTP Authentication and Web Server Access"
}
[/block]
Webhooks can be sent to any publicly accessible web server, on any port, with or without encryption. They can include a username and password for HTTP basic authentication.

## Specify a username and password
If your web server uses HTTP basic authentication, you can add the username and password to the URL before the host address. Special characters such as @ in the password should be percent-encoded.

**Example**: `http://username:password@app.acmemonitoring.com/pagerduty.php`

## Webhook Ports
If you specify `http://` in your Endpoint URL, we will initiate a standard HTTP connection on port 80. Likewise, entering `https://` means we will attempt to make a secure connection on port 443. To override the default port, add a colon (`:`) after the host address with the desired port number.

**Example**: `https://app.acmemonitoring.com:8443/pagerduty.php`

## Restrict access to just PagerDuty IPs

You can view our list of IPs to whitelist [here](/docs/whitelisting-ips#section-what-are-pagerdutys-ips-for-whitelisting-and-firewall-purposes).

## Can I use a self-signed certificate for webhooks?

Yes. Web servers presenting self-signed or expired certificates will receive webhooks.
[block:api-header]
{
  "title": "Temporary Blocks and Blacklisting"
}
[/block]
When a site goes down or responds with an error status, it is expected that events can't be received to your webhook, or that it will become completely disabled.

When events are sent to your webhook endpoints, PagerDuty expects a 200 response within 5 seconds. If there is no response, or if there is any response other than a 200, PagerDuty will periodically retry sending the webhook. 

## Server and Network Errors

If we receive a 5XX (server error) response from the receiving end, or can't establish a connection, or can't resolve the host name, it is considered a transient issue and retry logic is applied. First the event is rescheduled for delivery 50 seconds in the future. If it continues to 500, PagerDuty will back off by a multiple of 1.25^N for 7 more tries (8 retries total). This takes about 20 minutes.

## Client Errors

If we receive a 4XX (client error) response from the receiving end, the error is considered non-transient, and the webhook is dropped. If the number of dropped webhook events exceeds 8, the endpoint will be disabled.

## Temporary Disablement

After retries are exhausted or the maximum number of dropped webhook events is reached, the endpoint will be disabled for 30 minutes. PagerDuty will continue to accumulate events for the endpoint while it is disabled. Events will be scheduled for after the disable has expired. If the retries continue to fail, the endpoint will be disabled for exponentially longer periods of time (again, 1.25^N), up to 6 retries total (about 7.5 hours).

If PagerDuty still can't deliver a webhook event at that point, it will blacklist the endpoint and show that the webhook is disabled in the web app. Queued events will be discarded until a user manually unblocks it in the web UI.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f64047c-9ad95d5-webhook-disabled.jpg",
        "9ad95d5-webhook-disabled.jpg",
        1394,
        221,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
## Classification of Endpoints

Our webhook delivery service's retry/temporary blacklist logic groups and classifies webhooks according to their endpoint URL, and not by the service or distinct extension object itself. So, if you have two differently-named webhooks on two different services, but they both have the same endpoint URL, they will both be temporarily disabled if webhooks from one of them end up receiving error responses.