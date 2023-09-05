---
description: Using Make with SA5's Forms Handler
---

# ▶️ Make ( Integromat ) Handler

Make is a great choice for Webflow automation.&#x20;

* It offer a good range of integrations like Zapier, at a lower cost
* It support logic branching, which Zapier does not offer effectively
* It supports webhook responses, meaning you can return data to your Webflow site after processing a request. &#x20;

SA5's form handler uses these well.&#x20;

## Setting up your Make Scenario

{% hint style="info" %}
In Make, an automation flow is referred to as a **Scenario**.&#x20;
{% endhint %}

**Some tips for the best use of Make.**

If you specify a Request webhook only, with no response, Make will always return the plain-text response "Accepted". This works fine, but does not give you the ability to pass back any information or error messages.

If you use Response webhooks as well ( as in the scenario below ), you can return both data and error messages if your business logic calls for it. This makes it possible to give specific feedback to the user after they submit the form.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

Here's a walkthrough of the scenario setup.&#x20;

{% embed url="https://www.loom.com/share/f7ad76c67e72463296a5a09788182d41" %}

### Returning Data&#x20;

Use HTTP Response Codes to indicate success or failure.&#x20;

* Response codes in the 200-299 range will be recognized as a successful event by SA5 and we'll display the form success panel.&#x20;
* Response codes in the 400-599 range will be handled as errors, and we'll display the form's error panel.

## Best Practices

Use both Make's **Custom Webhook** and **Webhook Response** nodes together to communicate information back to your users. &#x20;

In your Webhook Response nodes-

* Use `2xx` codes on successful processing, and `4xx` or `5xx` codes for errors. [Choose codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) that are meaningful and make sense to your situation.&#x20;
* Set a response header to indicate a JSON response;
  * key: `Content-Type`
  * value: `application/json`
* Set the Body to a valid JSON string;
  * e.g. `{ "message": "Success." }`

Use Make's **Router** to configure a full range of success and error responses, as needed. &#x20;

[https://www.make.com/en/help/tools/webhooks](https://www.make.com/en/help/tools/webhooks)

## Future

We support basic text response messages and will document this if anyone needs more than a success/failure state.

We're likely to add a full JSON data package response, and callback to SA5.&#x20;

## Technical Notes

With no Webhook response node, Make always returns;&#x20;

`text/plain; charset=utf-8`, with a body of `Accepted`

When a Webhook response node is specified, Make returns JSON, e.g.; &#x20;

`application/json; charset=utf-8 { "message" : "YES! Message received." }`

`application/json; charset=utf-8 { "message": "This is our custom error message when we find ERROR in the name." }`

