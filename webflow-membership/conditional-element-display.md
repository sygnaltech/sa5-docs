# Conditional Element Display





{% embed url="https://wfu.sygnal.com/docs/webflow-membership/conditional-element-display/" %}

{% hint style="danger" %}
This is likely a temporary solution, as Webflow is building this feature into Memberships natively.
{% endhint %}

This feature allows you to hide/show elements based on the logged-in / logged-out state of the current user.

You can;

* Show elements only when logged-in
* Show elements only when logged-out

IMPORTANT: This only affects visible display, it does not prevent users from accessing that content if they view source.

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-show-logged-in` attribute <a href="#wfu-show-logged-in-attribute" id="wfu-show-logged-in-attribute"></a>

Add the `wfu-show-logged-in` custom attribute (no value needed) when you want an element to only appear to logged-in users.

#### `wfu-hide-logged-in` attribute <a href="#wfu-hide-logged-in-attribute" id="wfu-hide-logged-in-attribute"></a>

Add the `wfu-hide-logged-in` custom attribute (no value needed) when you want an element to only appear to NON-logged-in users.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/dist/css/webflow-membership.css">
```

Add this JS reference to the BODY of your site or page.

```
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/src/nocode/webflow-membership.js"></script>
```

#### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

\
