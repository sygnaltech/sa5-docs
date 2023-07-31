---
description: >-
  Add an adaptive preview link to your demo site, which will link to the correct
  page of your read-only preview.
---

# Webflow Preview Link ❺

Enables you to dynamically construct a Webflow preview link to the current page.

## What is a Preview Link? <a href="#what-is-a-preview-link" id="what-is-a-preview-link"></a>

In Webflow, a [preview link](https://university.webflow.com/lesson/share-your-project-and-invite-collaborators) is a special link that allows someone to view a read-only version of your Webflow site in the designer.

### What would you Use this for? <a href="#what-would-you-use-this-for" id="what-would-you-use-this-for"></a>

If you develop Webflow sites, and want to make it easy for someone to click a button that switches the current page into a design mode view, this utility enables that.

## Demonstration <a href="#how-to-use-it" id="how-to-use-it"></a>

{% embed url="https://webflow-smart-elements.webflow.io/demo" %}

## How to Use it <a href="#how-to-use-it" id="how-to-use-it"></a>

* You must have created a preview link to your site, and extract the preview link Id. It looks something like this- `4d388483d99c6cc36c58ae966e92c615`.

Limitations;

* Does not work with Collection pages, since they require an additional collection item ID that is not emitted into the page.

## Implementation <a href="#implementation" id="implementation"></a>

Add this code to the **before BODY** of your site or page.&#x20;

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.11/dist/css/webflow-demo.css">
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.11/dist/nocode/webflow-demo.js"></script>
```
{% endcode %}
