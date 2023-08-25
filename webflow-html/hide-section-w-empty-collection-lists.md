---
description: Hide an entire section when the collection lists in it are empty
---

# Hide Section w/ Empty Collection Lists ❺

Suppose you have an area of your page called “alerts” and it has some nice styling and icons… but sometimes, there are no alerts to show. How do you make the whole thing disappear when there are no alerts in the Collection List for display?

This solution provides two simple attributes-based methods to do just that.

## Demonstration <a href="#usage-notes" id="usage-notes"></a>

{% embed url="https://webflow-smart-elements.webflow.io/hide-empty-collection-lists" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

We have two slightly different solutions here, depending on your needs. In both solutions, if ALL of the collection lists within the attribute-tagged section are empty, the entire section will be hidden.

**Click the toggle next to the solution you want.**

If you want a solution that works with all browsers, use the _suppress_ feature.

<details>

<summary>I want to SUPPRESS a section whose collection lists are all empty</summary>

To the section you want to hide, add the custom attribute;&#x20;

```
wfu-suppress = empty-lists
```

</details>

If you need a solution that is _dynamic_, and can respond to changes _after the page has loaded_ - such as those made by Finsweet's CMS Filter - use this solution. However the CSS technique used here is not supported by Firefox.&#x20;

<details>

<summary>I want to HIDE a section whose collection lists are all empty </summary>

To the section you want to hide, add the custom attribute;

```
wfu-hide = empty-lists
```

</details>

{% hint style="success" %}
To recap;

**Hide** mode is CSS-based and will not work with Firefox- however it is dynamic and will work with Finsweet's CMS filter.

**Suppress** mode is JS-based and will work with all browsers- however it executes at page load time, and will not respond to dynamic list changes after the page has loaded.
{% endhint %}

## Technical Notes <a href="#getting-started-nocode" id="getting-started-nocode"></a>

**Hide** mode is 100% CSS-based, and leverages the  `:has()` pseudoselector. However this CSS feature is not yet [supported](https://caniuse.com/css-has) by all browsers, most notably Firefox. If you need 100% browser coverage, you should use our **Suppress** mode until Firefox implements :has fully.&#x20;

{% hint style="info" %}
As of Aug-2023, Firefox has about 7% desktop share, but almost 0% mobile. If your site primarily targets mobile users, Firefox's lack of support for CSS :has will not affect you.&#x20;
{% endhint %}

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply `wfu-hide` or `wfu-suppress` to the sections you want to hide <a href="#step-2---apply-wfu-hide-section-or-element-you-want-to-hide" id="step-2---apply-wfu-hide-section-or-element-you-want-to-hide"></a>

See above for details.

\
