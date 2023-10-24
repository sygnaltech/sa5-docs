---
description: >-
  Post form data direct to webhooks, while supporting Webflow's inline success /
  error messages
---

# Smart Form Webhook Handler ❺

{% hint style="warning" %}
v5.3.7 has redefined the `other` handler to recognize error codes as errors, and to display the form's error message accordingly. If you need the original behavior where success is assumed regardless of the response code, use the new `success` handler.&#x20;
{% endhint %}

{% hint style="success" %}
v4.10 adds [Basin](https://usebasin.com/) support, to help alleviate SPAM and form handler issues.
{% endhint %}

{% hint style="info" %}
Currently supports HTTP POST to webhooks only. We may add HTTP GET support if users are in need of it. Use the forum to suggest future improvements.&#x20;
{% endhint %}

## Overview

Webflow has a nice form-builder capability with good styling options- however by default, the success and failure messages _only_ work with Webflow's built-in form handler.

**SA5 Forms** allows you to integrate Webflow forms with other services, and process their responses as success / fail, including error message and results display.&#x20;

## Demonstration

{% embed url="https://webflow-forms-demo.webflow.io/auto/zapier-webhook" %}

## Details

Webflow forms can be redirected to a webhook for external processing, by specifying the `action` in Webflow’s designer. This gives you a lot of capability, including business logic and immediate processing of your form data, however Webflow does not have any in-built way to handle the webhook’s response.

By default, instead of a “success” message, the user sees the JSON response itself- which is not an ideal user experience. Alternatively, you’re forced to create a thank you page, exclude it from search engines, etc- when often all you wanted was a success message.

The WFU forms handler bridges that gap;

1. It submits your form directly to the webhook you choose.
2. It analyzes the response to determine success or failure.
3. It then displays the form success or failure message, depending on that result.
4. On a successful submit, if the form is configured with a redirect URL, then the submit button is given the _Please wait..._ text and the page is redirected instead. &#x20;

## Webhook Handlers

Because each webhook provider responds differently, we have several “handlers” for each situation;

* The **Zapier** handler looks for “success” in the response, and displays the success message if it is present. However it’s important to note that Zapier’s success response only indicates that the data was received successfully. It does not indicate that the Zap ran successfully.
* The **Make** ( Integromat ) handler can handle specific responses and display error messages, if you use the HTTP Response node in Make. If you have the request return immediately, you will simply get 'Accepted' from Make as the success text.&#x20;
* The **n8n** handler can handle specific responses and display error messages.
* The **Basin** handler shows success and fail messages depending on [Basin](https://usebasin.com/)'s response.
* The **Other** handler is most useful for unknown webhook providers. It relies on the webhook to return a meaningful response code. Responses in the range 200-299 are considered success, and anything else is considered an error. Use it for simple and less essential form submissions, like newsletter enrollments.
* The **Success** handler _always_ displays the success message, regardless of the response code. Use it in situations where success/failure aren’t that important, you just need to indicate to the user that their work is done.

## Key advantages <a href="#key-advantages" id="key-advantages"></a>

Why use a custom webhook form handler rather than Webflow's?

* Immediate form processing, with no delays. If you’ve used e.g. Zapier’s Webflow trigger, it polls for new forms and can take 10 minutes for a form submission to be detected.
* No need to use Webflow’s built-in forms email notification system. You can go direct to a Sales Force Automation (SFA) system, or to your own email notification with no unsubscribe link problems.
* No form submission limits.
* Make the form behave like a normal webflow form post, where it stays on the same page, and displays the form’s success message.
* Handle error scenarios better, including unique server side logic and error messages ( with Make & n8n ).

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start/).&#x20;

### STEP 2 - Setup your webhook handlers, and link your Webflow form <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>

* Setup your webhook on Basin, Zapier, Make, n8n, or your form handler or automation provider of choice. Design it to accept HTTP POST requests.
* Copy the webhook URL and in the Webflow designer, paste it into the `Action` setting of the form.
* Design the form however you like
* Set the form method to POST
* Make sure to customize your success and fail messages too.

### STEP 3 - Mark your Form for WFU’s handler <a href="#step-3---mark-your-form-for-wfus-handler" id="step-3---mark-your-form-for-wfus-handler"></a>

In the designer, select the `Form Block` element ( not the `Form` element ). On the `Form Block` element, add a custom attribute of `wfu-form-handler`, and specify the handler you want;&#x20;

* Use `basin` for [Basin](https://usebasin.com/) webhooks.
* Use `zapier` for Zapier webhooks.
* Use `make` for Make ( Integromat ) webhooks.
* Use `n8n` for n8n webhooks.
* Use `other` for all other webhooks.
* Use `success` to assume success on any response.&#x20;

Each will behave slightly differently in how it processes the response, since each webhook service does responses differently. See notes above.&#x20;

## Additional References

{% embed url="https://webflow-forms-demo.webflow.io/auto/zapier-webhook" %}

{% embed url="https://webflow-forms-demo.webflow.io/auto/webhook-success" %}
