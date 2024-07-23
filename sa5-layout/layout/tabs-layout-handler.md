---
description: Generate CMS-bound tabs and nested tabs
---

# Tabs Layout Handler

## Use Cases

* Create tabs from CMS content
* Create nested tabs from two collection lists in a master-detail arrangement
  * e.g. Countries and Cities&#x20;

## Usage Notes

SA5 automatically detects when the wfu-layout attribute is positioned on a tabs element, and will create tabs automatically.&#x20;

wfu-layout-handler = auto | none | tabs

Default is auto, when unspecified.&#x20;

## Demonstration

[https://cms-layouts.webflow.io/](https://cms-layouts.webflow.io/)



## Technical Notes

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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













