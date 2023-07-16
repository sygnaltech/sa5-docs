---
description: Detect Webflow breakpoint changes, in code
---

# Breakpoints ❺

## Overview

Webflow has 7 distinct breakpoints that act as the center of its responsive design methodology throughout the designer and in its published sites.&#x20;

Not only are all styles tied to breakpoints, but interactions can be as well.

_But what about your custom code?_&#x20;

Now, there's a way to do that too.&#x20;

## Use Cases

* Manipulate DOM or UX aspects that are beyond the capabilities of pure CSS or styles.
* A great example of this is our responsive pagination example that uses our breakpoints library with custom code to update Finsweet's CMS Load APIs.&#x20;
* Reload an IFRAME or other element that cannot adapt responsively across breakpoint changes.&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

When you include this library in your site or page, you can easily add a custom code callback to handle events when the breakpoints change.

Here's what that would look like;

```html
<script>
window.sa5 = window.sa5 || {};
window.sa5.breakpointChanged = 
  (name, breakpoint) => {
   console.log("BREAKPOINT", name); 
  };
</script>
```

In this example, we register a breakpoint handler that is fired on the page's first load, and any time the breakpoint changes.

It will always contain one of the following values;

* large1920
* large1440
* large1280
* desktop
* tablet
* mobileLandscape
* mobilePortrait

Based on the value you get, you can perform whatever scripting you like.&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

{% hint style="info" %}
This feature is using WFU's v5 new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;

You can use both the v4 and v5 libraries simultaneously to get the full feature set during migration.
{% endhint %}

Add this to the **before HEAD** custom code area of your site or page.

{% code overflow="wrap" %}
```html
<script defer
src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.1.1/dist/nocode/webflow-html.min.js"
></script> 
```
{% endcode %}

Nothing is needed in the before BODY code area.&#x20;

### STEP 2 - Implement your callback handlers <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

See above for details.

## Resources

{% embed url="https://university.webflow.com/lesson/custom-attributes" %}

{% embed url="https://webflow.com/feature/use-cms-data-in-custom-attributes" %}
