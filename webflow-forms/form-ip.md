# Form IP

### DEMO - Webflow Forms w/ IP Info <a href="#demo---webflow-forms-w-ip-info" id="demo---webflow-forms-w-ip-info"></a>

[View Demonstration in Webflow](https://webflow-forms-demo.webflow.io/special/ip-info)

Captures the sender’s IP info and appends it to the tagged form as hidden fields.

Why?

* Capture general geographic info, such as country and city.
* Store IP ( where permitted, and part of your privacy policy ), as a verification of the send. Required by some services like Mailchimp, for loading external lists.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Install this JS in BODY, site-wide or on the specific pages you want the script to affect.

{ $book.variables }

\{{ book.version \}}

{ $book.variables.version }

{ $book.version }

Test book&#x20;

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.34/src/nocode/webflow-form.js"></script>
```
{% endcode %}

#### STEP 2 - Tag your For Block <a href="#step-2---tag-your-for-block" id="step-2---tag-your-for-block"></a>

`[wfu-form-ipinfo]`

\
