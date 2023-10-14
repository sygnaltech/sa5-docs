---
description: Interact with Webflow's Tabs Element
---

# Future

Plan to add;&#x20;

* Console log error if more than one tab element is accidentally assigned the same unique name.&#x20;

Some things we're considering;&#x20;

{% hint style="danger" %}
These are under consideration for implementation, and not yet implemented.&#x20;
{% endhint %}

### Pre-change event

Fire an event before a tab change happens, and allow the responding code to approve/deny the change. This is very interesting, for special flows such as multi-step forms.&#x20;

However it requires;

* Completely overriding the default webflow.js event handler
* Replacement of that default handler with an SA5 variant&#x20;
* An event origination flag, i.e. user-initiated v. code-initiated&#x20;

### `wfu-tabs-action` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

I want a button or link to change tabs by index or text label.

To any button or link, you can define an action;

* first - select the first tab
* prev - select the previous tab
* next - select the next tab
* last - select the last tab
* <mark style="color:orange;">goto - select the specified tab</mark>
* <mark style="color:orange;">goto ( name ) - matches first one only, starting from tab 1</mark>&#x20;

### `wfu-tabs-action-tab` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

For the goto action, specifies the tab you want to navigate to.&#x20;

* <mark style="color:orange;">number - indicates the tab index, 0, 1, 2...  ( index )</mark>
* <mark style="color:orange;">name - matches first one only, starting from tab 1</mark>&#x20;

## Change on Hover <a href="#getting-started-nocode" id="getting-started-nocode"></a>

[https://discourse.webflow.com/t/open-tab-pane-on-hover-instead-of-click/218539/3](https://discourse.webflow.com/t/open-tab-pane-on-hover-instead-of-click/218539/3)

## Select on Query or #&#x20;









