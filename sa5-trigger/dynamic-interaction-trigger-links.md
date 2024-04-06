---
description: Trigger Your Click Interactions with Links
---

# Dynamic Interaction Trigger Links ❺

Webflow's interactions are powerful, but they are not easily script-accessible. Our goal is to make them even more useful by making them easier to trigger specific interactions from dynamic content such as rich-text links throughout your page.

## Use Cases

Perhaps the most common use case for this is triggering modal pop-ups. &#x20;

* Trigger a CTA pop-up from text-links easily, even within CMS rich text content like a blog post.
* Trigger CMS-based pop-ups similarly, but targeting the exact pop-up you want. Different offers, different CTA's, additional info, or display a definition when someone clicks a glossary term. &#x20;

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

## Considering <a href="#getting-started-nocode" id="getting-started-nocode"></a>

wfu-ix-trigger-type ( optional ) = click | timer

wfu-ix-trigger-ms = 10000

## Use Cases

Trigger -> Interaction

### You want to click an element, and have an interaction run



### You want to click a link, like a dictionary definition or a map pin, and have an interaction run

This data may be from the CMS&#x20;

### You want an interaction to trigger automatically after N seconds





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

