---
description: Capture specific hotkeys to perform specific tasks
---

# Hotkeys ❺

## Overview

Supercharge your site by providing quick capabilities through hotkeys.

* Help menus
* Filter reset
* Navigation

## Use Cases

* F1 - show your own help menus
* ESC - filter reset
* CTRL+P - user account custom preferences&#x20;

Best practices;

* Seek to avoid common browser hotkeys.
* Generally, stick with function keys and modifier keys&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

When you include this library in your site or page, you can easily add a custom code callback to handle events when the breakpoints change.

Here's what that would look like;

```html
<script>
window.sa5 = window.sa5 || {};
window.sa5.hotkeys = (hotkeyHandler) => {
  hotkeyHandler.register("f2", () => {
    console.log("f2 pressed");
  });
}
</script>
```

Based on the hotkey pressed, you can perform whatever scripting you like.

The hotkeys you want are described in the first parameter of the register function. You can have modifier keys, and you can have multiple keys assigned to the same handler event.

Here are some examples;

* ctrl+alt+q - modifier keys
* ctrl+a,ctrl+b,r,f - multiple hotkeys on the same handler
* ⌘+s,ctrl+s - Apple and Windows

## Technical Notes

Based on [Hotkeys.js](https://github.com/jaywcjlove/hotkeys-js).

Hotkeys.js has been tested and should work in.

```
Internet Explorer 6+
Safari
Firefox
Chrome
```

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
<!-- Sygnal Attributes 5 | Hotkeys -->
<script defer
src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2/dist/nocode/webflow-hotkeys.min.js"
></script> 
```
{% endcode %}

Nothing is needed in the before BODY code area.&#x20;

### STEP 2 - Implement your callback handlers <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

See above for details.

## Resources

{% embed url="https://github.com/jaywcjlove/hotkeys-js" %}
