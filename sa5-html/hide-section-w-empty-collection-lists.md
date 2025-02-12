---
description: Hide an entire section when the collection lists in it are empty
---

# Hide Section w/ Empty Collection Lists ❺

In page designs, there is often a need for an entire section to completely disappear when it has no CMS data to show.&#x20;

Consider this section;

```
DIV - News Section
  Heading - "Recent news"
  Collection List - News, filtered to past 30 days 
```

Webflow offers a "no items found" state for the collection list itself- however in this case, when there is no recent news to show, we may want the entire section to simply disappear.&#x20;

_This solution provides two simple attributes-based methods to do just that._&#x20;

## Use Cases

* News sections
* Alerts bars
* Popup special
* Finsweet filtered views &#x20;
* etc.&#x20;

## Demonstration <a href="#usage-notes" id="usage-notes"></a>

{% embed url="https://webflow-smart-elements.webflow.io/hide-empty-collection-lists" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

## Getting Started <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Add the Attributes  <a href="#step-2---apply-wfu-hide-section-or-element-you-want-to-hide" id="step-2---apply-wfu-hide-section-or-element-you-want-to-hide"></a>

Apply _either_ `wfu-hide` or `wfu-suppress` to the sections you want to hide.&#x20;

_See below for the differences, and usage details._

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

We have two slightly different solutions here, depending on your needs. &#x20;

* `wfu-hide` - Hides the section when all collection lists within it are empty&#x20;
* `wfu-suppress` - Removes the section when all collection lists within it are empty&#x20;

{% hint style="success" %}
In both solutions, if ALL of the collection lists within the attribute-tagged section are empty, the entire section will be hidden.&#x20;
{% endhint %}

### `wfu-hide` = `empty lists`

_Hides_ the section when all collection lists within it are empty.&#x20;

Add this attribute directly to the section you want hidden. &#x20;

{% hint style="info" %}
**Hide** mode is CSS-based- however it is dynamic and will work with Finsweet's CMS filter.
{% endhint %}

### `wfu-suppress` = `empty lists`

_Removes_ the section when all collection lists within it are empty. &#x20;

Add this attribute directly to the section you want suppressed.&#x20;

{% hint style="info" %}
**Suppress** mode is JS-based and will work with all browsers- however it executes at page load time, and will not respond to dynamic list changes after the page has loaded.
{% endhint %}

### What's the Difference?&#x20;

Here are the differences between the two attributes.&#x20;

|                                                                 | wfu-hide                                                                                                                                                                                                                                                         | wfu-suppress                                                                                                                                                                                                      |
| --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How it works                                                    | Hides the section the attribute is on, using CSS display: none.                                                                                                                                                                                                  | Removes the section entirely.                                                                                                                                                                                     |
| Browser support                                                 | All browsers, including newer versions of Firefox since early 2024                                                                                                                                                                                               | All browsers                                                                                                                                                                                                      |
| Compatibility with Finsweet Attributes like FS Load & FS Filter | Compatible; can dynamically adapt to changing conditions of the list content after the page has loaded and filter settings are changed.                                                                                                                          | Not compatible, runs once at page load and will permanently remove the section.                                                                                                                                   |
| Which should I choose?                                          | <p>In general, we recommend that you use <code>wfu-hide</code>.<br></p><p>If you need a solution that is <em>dynamic</em>, and can respond to changes <em>after the page has loaded</em> - such as those made by Finsweet's CMS Filter - use this solution. </p> | Use `wfu-suppress` if you need to support older versions of Firefox, or other browsers that do not support CSS [:has()](https://caniuse.com/css-has) or CSS [:not()](https://caniuse.com/mdn-css_selectors_not).  |



## Technical Notes <a href="#getting-started-nocode" id="getting-started-nocode"></a>

**Hide** mode is 100% CSS-based, and leverages the  `:has()` pseudoselector. However this CSS feature is not yet [supported](https://caniuse.com/css-has) by all browsers, most notably Firefox. If you need 100% browser coverage, you should use our **Suppress** mode until Firefox implements :has fully.&#x20;

{% hint style="info" %}
As of Aug-2023, Firefox has about 7% desktop share, but almost 0% mobile. If your site primarily targets mobile users, Firefox's lack of support for CSS :has will not affect you.&#x20;
{% endhint %}

\
