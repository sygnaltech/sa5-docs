# Form IP Info

#### DEMO - Webflow Forms w/ IP Info <a href="#demo---webflow-forms-w-ip-info" id="demo---webflow-forms-w-ip-info"></a>

[View Demonstration in Webflow](https://webflow-forms-demo.webflow.io/special/ip-info)

Captures the sender’s IP info and appends it to the tagged form as hidden fields.

Why?

* Capture general geographic info, such as country and city.
* Store IP ( where permitted, and part of your privacy policy ), as a verification of the send. Required by some services like Mailchimp, for loading external lists.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### **STEP 1 - Add the Library**

Install this JS in BODY, site-wide or on the specific pages you want the script to affect.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.34/dist/css/webflow-html.css">
```
{% endcode %}

Add this JS reference to the BODY of your site or page.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.34/src/nocode/webflow-form.js"></script>
```
{% endcode %}

### **STEP 2 - Tag your Form Block**

Place this custom attribute on your form block element;

`[wfu-form-ipinfo]`

