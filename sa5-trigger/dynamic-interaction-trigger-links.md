---
description: Trigger Your Click Interactions with Links
---

# Dynamic Interaction Trigger Links ❺

**Webflow's interactions are powerful, but they are not easily script-accessible.**&#x20;

Our goal is to make them even more useful by making them easier to trigger specific interactions from dynamic content such as rich-text links throughout your page.

## Use Cases

Perhaps the most common use case for this is triggering Interaction-based modal pop-ups;

* Trigger a CTA pop-up from text-links easily, even within CMS rich text content like a blog post.
* Trigger CMS-based pop-ups, targeting the exact pop-up you want. Different offers, different CTA's, additional info, or display a definition when someone clicks a glossary term. &#x20;

Although we primarily use this as an interaction trigger, you can think of this more as a proxy-click capability. This means that you can similarly trigger a tab change, a form submission, a slider advance, or anything else that can be clicked.&#x20;

## Special Note

Once you've setup your interactions and click-triggers as described below, you can trigger your named interactions in one of two ways-

You can assign a custom attribute to the button or element you want to use as a trigger, with a value identifying the specific interaction you want to fire.

Or as a shortcut, we have a special link format.

`##my-interaction-id`

Link anything and set the URL to a double-hash `##` link with the name of the interaction you want to trigger.&#x20;

For example,&#x20;

* `##cta1` can launch your CTA #1 pop-up
* `##enroll` can launch a pop-up form for enrollment&#x20;
* `##llm`, `##ai`, and `##chatgpt` can all be connected to CMS-driven pop-ups to drive a glossary of terms&#x20;
* `##p0543` can display a modal with product or product-category information from your ECommerce store

Because these are set as the link URLs, the test displayed to the user can be anything you like.

## Usage Notes

### Basic Setup

* Create your interaction to do whatever you want
* Create a button element, and set it to trigger your interaction on click
* Assign the `[wfu-ix-id]` attribute to that button element, and give it a unique ID
* Now on any link or button anywhere in your page, you can assign a `[wfu-ix-trigger]` attribute to that element
* Or, in any link on your page, assign a URL with `##` with the ID you've assigned to the interaction you want

Now, clicking any of those links will trigger your interactions.&#x20;

### Advanced Setup

When you are want CMS-sourced modals such as product pop-ups or glossary pop-ups, here are some tips;

* Design your modal first
* Place it inside of your CMS Collection List
* Place your triggering button as an immediate sibling of your modal's parent element
* In your interaction, trigger the modal _by class_, targeted to _sibling elements only_. That will give much more reliable results&#x20;
* Assign your `[wfu-ix-id]` custom attribute to that button, and set the value using Webflow's CMS data-binding feature, to the `slug` of the collection item

Now, anywhere in your page, you can link to `##slug` to trigger that item.&#x20;

## Use Cases

### You want to click an element, and have a popup appear

* Create your interaction-based popup so that it is triggered by a button. The button can be hidden, but it is needed to invoke the interaction.&#x20;
* Add the `wfu-ix-id` custom attribute to that button&#x20;
* To the triggering element, add the `wfu-ix-trigger` attribute  &#x20;

### You want to click a text link, like a dictionary definition, product, or a staff member's name, and have a link-specific pop-up appear&#x20;

* Create your interaction-based popup so that it is triggered by a button. The button can be hidden, but it is needed to invoke the interaction.&#x20;
* Add the `wfu-ix-id` custom attribute to that button&#x20;
* In your text, create any link you want, and set the link href so that it begins with `##` and then the ID you've assigned to the your modal button&#x20;

You can generate the modals and their triggering buttons from the CMS, and use the slug as the ID.  This makes it easy for you to invoke CMS-generated popups. &#x20;

### You want an interaction to trigger automatically after N seconds

FUTURE.&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

There are currently no configuration options for the data-binding feature, so we’ll use a _no-code_ integration approach.

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../sa5-url/quick-start.md).

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Install this code in **before HEAD**, site-wide or on the specific pages you want the script to affect.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Interactions --> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.25/dist/nocode/webflow-ix.js"></script> 
```
{% endcode %}

### STEP 2 - Setup your data-binding attributes <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>

Apply the attributes you want. See above.&#x20;

