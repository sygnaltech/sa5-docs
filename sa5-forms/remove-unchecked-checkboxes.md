# Remove Unchecked Checkboxes ✨

On form submission, it can be difficult to deal with email notifications that contain a huge pile of "false" values. &#x20;

This attribute will cause those checkbox values to be removed just prior to the form submission, to ensure they do not clutter your email notifications unnecessarily.

## How it Works

On form submission,&#x20;

* The form is validated to ensure that the submission will be successful.
* If valid, any unchecked checkboxes are then removed so that you will have no false values in your email or in your form history&#x20;
* The form submission is then completed, and Webflow's form handler or your custom form handler&#x20;

{% hint style="success" %}
Webflow's email notifications and form submission history handle this very well.  The email simply does not contain those items, and the form submission history shows blanks in those columns rather than `false` values.&#x20;
{% endhint %}

{% hint style="warning" %}
Not tested with reCaptcha- it's possible that if the form is valid, but reCaptcha is not, that the fields could be removed from the form, but the form submission could be prevented by the reCaptcha fail.  This is a rare edge case but worth testing if it's important to your situation.
{% endhint %}

## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

First, **add the library** as detailed in [Quick Start](quick-start/).&#x20;

## Required Attributes

### Add `wfu-form`&#x20;

Add `wfu-form` to the **form** or **form block** element directly.&#x20;

### Add `wfu-form-checkbox`&#x20;

Designate the checkboxes you want removed-if-unchecked with the following attribute and value-

`wfu-form-checkbox` = `remove-unchecked`&#x20;

* Apply this to the element with `wfu-form` on it, if you want all checkboxes to be affected
* Apply this to an **individual checkbox** element if you want only specific checkboxes to be affected

<figure><img src="../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

* Apply this to a grouping element such as a DIV, if you want a specific group of checkboxes to be affected

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
You can use this attribute on multiple checkbox elements and/or groups.&#x20;
{% endhint %}

## Optional Attributes  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

_None._

















