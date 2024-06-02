---
description: Capture specific hotkeys to perform specific tasks
---

# Hotkeys ❺

We use hotkeys all the time, like CTRL+C... but did you know that you can create hotkeys uniquely for your website?&#x20;

This is useful for all sorts of things...&#x20;

* Help menus
* Search
* Filter resets
* Navigation
* Admin shortcuts, like switch-to-edit-mode&#x20;

## Use Cases

Here are a few examples;&#x20;

* `F1` - show your own help menus
* `ESC` - filter reset
* `CTRL+P` - user account custom preferences&#x20;

Best practices;

* Seek to avoid common browser hotkeys.
* Generally, stick with function keys and modifier keys&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

When you include this library in your site or page, you can easily add a custom code callback to handle events when the breakpoints change.

Here's what that would look like;

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['hotkeys', (hotkeyHandler) => {
  hotkeyHandler.register("f2", () => {
    console.log("f2 pressed");
  });
}]);
</script>
```

Based on the hotkey pressed, you can perform whatever scripting you like.

The hotkeys you want are described in the first parameter of the register function. You can have modifier keys, and you can have multiple keys assigned to the same handler event.

Here are some examples;

* `ctrl+alt+q` - modifier keys
* `ctrl+a,ctrl+b,r,f` - multiple hotkeys on the same handler
* `⌘+s,ctrl+s` - Apple and Windows

This setup is also designed so that you can have register hotkeys in multiple separate code blocks on the same page. Why would want to do that?&#x20;

* Register some hotkeys in your site-wide code, so that they work on all pages
* Register additional hotkeys on a specific page or collection page
* Register additional hotkeys in a custom code element, within a component, so that they travel with that component anywhere you use it &#x20;

## Technical Notes

Based on [Hotkeys.js](https://github.com/jaywcjlove/hotkeys-js).

Hotkeys.js has been tested and should work in.

* Chrome
* Safari
* Firefox&#x20;
* Internet Explorer 6+&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

There are currently no configuration options for the data-binding feature, so we’ll use a _no-code_ integration approach.

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Implement your callback handlers <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

See above for details.

## Resources

{% embed url="https://github.com/jaywcjlove/hotkeys-js" %}
