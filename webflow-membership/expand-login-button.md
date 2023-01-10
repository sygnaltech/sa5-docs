# Expand Login Button

{% embed url="https://wfu.sygnal.com/docs/webflow-membership/expand-login-button/" %}

### Expand the Login Button with a Container <a href="#expand-the-login-button-with-a-container" id="expand-the-login-button-with-a-container"></a>

Used to expand Webflow’s current Log-In / Log-Out button with a container To include an icon, etc.

See https://sygnal.com for an example ( top right ).

* Make your login button include an icon, or additional text
* Create a larger area
* Wrap it in a menu style container

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### Create a DIV, with the `wfu-login-button` attribute <a href="#create-a-div-with-the-wfu-login-button-attribute" id="create-a-div-with-the-wfu-login-button-attribute"></a>

* Add the `wfu-login-button` custom attribute (no value needed) to identify the clickable “expanded login button” element.
* Include whatever else you want in that button DIV
* Style it however you like

#### Place the Webflow Log-In / Log-Out Button inside of it <a href="#place-the-webflow-log-in--log-out-button-inside-of-it" id="place-the-webflow-log-in--log-out-button-inside-of-it"></a>

This is important, it’s the inner element that the expanded button will perform the log-in / log-out action through.

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
