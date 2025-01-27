---
description: Generate CMS-bound tabs and nested tabs
---

# Tabs Layout Handler

SA5 automatically detects when the `wfu-layout` attribute is positioned on a tabs element, and will create tabs automatically.&#x20;

## Use Cases

* Create tabs from CMS content
* Create nested tabs from two collection lists in a master-detail arrangement
  * e.g. Categories and Products&#x20;
  * e.g. Countries and Cities&#x20;

## Demo

{% embed url="https://sa5-layout.webflow.io/tabs" %}
Demo
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/sa5-layout" %}
Cloneable
{% endembed %}

## Usage Notes

Create and style your tabs element anywhere you like in your Webflow design.&#x20;

### Setup your tabs element&#x20;

`wfu-layout` = ( name )

Add this directly to your tabs element, and assign it a unique name in your page.

`wfu-layout-handler` = `auto` | `none` | `tabs`

* `auto` ( default) - automatically detect
* `none` - no layout engine needed, items are simply moved into the container
* `tabs` - use the tabs layout handler

Place on any element which has the `wfu-layout` attribute.&#x20;

In `auto` mode, SA5 automatically detects when the `wfu-layout` attribute is positioned on a tabs element, and will create tabs automatically.&#x20;

### Setting tab names

The tabs themselves are given a text name;

`wfu-layout-item-name` = ( name )&#x20;

Place this on any element with the `wfu-layout-target` attribute.&#x20;

{% hint style="info" %}
You can CMS-bind this attribute as well to pull the tab name from the CMS.
{% endhint %}

### Initializing the tabs element&#x20;

Here are some options on initializing the tabs element

`wfu-layout-init` = ( setting )

* `clear` - Removes any existing tabs before adding the new ones

`wfu-preload` = ( setting )

* `hidden` - Hides the tabs element on page load, until they're rendered.&#x20;

## Demonstration

[https://cms-layouts.webflow.io/](https://cms-layouts.webflow.io/)



## Technical Notes

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
This is the most basic Tabs rendition created, before webflow.js has initialized it.&#x20;
{% endhint %}

{% code overflow="wrap" %}
```html
<div wfu-tabs-target="_main" data-current="Tab 1" data-easing="ease" data-duration-in="300" data-duration-out="100" class="w-tabs">
   <div class="w-tab-menu">
      <a data-w-tab="Tab 1" class="w-inline-block w-tab-link w--current">
         <div>Tab 1</div>
      </a>
      <a data-w-tab="Tab 2" class="w-inline-block w-tab-link">
         <div>Tab 2</div>
      </a>
      <a data-w-tab="Tab 3" class="w-inline-block w-tab-link">
         <div>Tab 3</div>
      </a>
   </div>
   <div class="w-tab-content">
      <div data-w-tab="Tab 1" class="w-tab-pane w--tab-active"></div>
      <div data-w-tab="Tab 2" class="w-tab-pane"></div>
      <div data-w-tab="Tab 3" class="w-tab-pane"></div>
   </div>
</div>
```
{% endcode %}













