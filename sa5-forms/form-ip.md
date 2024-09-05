---
description: >-
  Capture the current user's IP and geo-location data as part of your form
  submits.
---

# Form IP Info ❺

Captures the sender’s IP and geolocation info and appends it to the tagged form as hidden fields.

## Demonstration <a href="#demo---webflow-forms-w-ip-info" id="demo---webflow-forms-w-ip-info"></a>

{% embed url="https://webflow-forms-demo.webflow.io/special/ip-info" %}
Demonstration
{% endembed %}

## Use cases

* Capture general geographic info, such as country and city.
* Store IP ( where permitted, and part of your privacy policy ), as a verification of the send. Required by some services like Mailchimp, for loading external lists.&#x20;

## Getting Started <a href="#getting-started-nocode" id="getting-started-nocode"></a>

* First, **add the library** as detailed in [Quick Start](quick-start/).&#x20;
* **Tag your Form Block.** Place this Place this custom attribute on your form block element:&#x20;

`[wfu-form-ipinfo]`

### Handler Options&#x20;

Currently the only supported handler is **GeoJS**.

{% embed url="https://www.geojs.io/" %}

### Sample Data

This is an example of the data appended to the form.

The `name` and `value` fields come through with your form content. \
Only non-blank results will be sent.&#x20;

```html
<input type="hidden" name="ip-ip" value="125.236.192.7">
<input type="hidden" name="ip-continent_code" value="OC">
<input type="hidden" name="ip-country" value="New Zealand">
<input type="hidden" name="ip-country-code" value="undefined">
<input type="hidden" name="ip-region" value="Auckland">
<input type="hidden" name="ip-city" value="Auckland">
<input type="hidden" name="ip-timezone" value="Pacific/Auckland">
<input type="hidden" name="ip-latitude" value="-36.8506">
<input type="hidden" name="ip-longitude" value="174.7679">
```

## Future

* Separate this data lib from the data-binding lib, and allow it to be used independently.&#x20;



