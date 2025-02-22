---
description: Trigger Your Click Interactions with a Link click
---

# IX Triggers ( Legacy ) ❺

**Webflow's interactions are powerful, but they are not easily triggered from JavaScript.**&#x20;

This library is designed to make interactions easier to trigger and easier to associate with specific CMS items, to open up a range of use cases.&#x20;

{% hint style="warning" %}
This documentation refers to SA5's Legacy trigger concept, defined by the `wfu-ix-*` attribute namespace.  This piece is fully functioning, but will likely be absorbed into the new SA6 Trigger architecture, and the attribute names will likely update with that.&#x20;
{% endhint %}

## Use Cases

* Interactions-based CMS-driven pop-ups triggered;&#x20;
  * from within within a slider or other overflow: hidden container, where the modal would be cut off if it were placed inside of the slider with the trigger button.&#x20;
  * from a script-generated map pin&#x20;
  * from simple user-generated links within a blog or article text
  * from script-generated text links such as automatically tagged glossary terms with a definition pop-up&#x20;
* Other complex CMS-based modal + trigger setups&#x20;

Although we primarily use this as an interaction trigger, you can think of this more as a CMS-friendly proxy-click capability. This means that you can similarly trigger a tab change, a form submission, a slider advance, or anything else that can be clicked.&#x20;

## How Does it Work?&#x20;

The basic idea is a very simple proxy-click.&#x20;

* You build your normal interactions setup, such as a set of CMS-driven modals ( rightmost collection list here )&#x20;
* You setup a hidden trigger button for each modal, that targets the interaction relative relative to the button, e.g. parent-only or sibling-only.  This ensures you only display the desired popup.&#x20;
* That trigger button is then tagged with some custom attributes so that the SA5 scripts can identify it easily.&#x20;
* You generate a second collection list ( shown leftmost here ), which generates the buttons you want users to see.  These proxy buttons are also tagged with attributes to match them up to the hidden buttons you want to trigger.&#x20;
  * This can be used with Finsweet CMS Slider to generate slides
  * They can be rendered as map pins&#x20;
  * Or any other setup you want
* SA5's Trigger lib identifies both the trigger buttons and the proxy buttons, and establishes click handlers. Any click on the proxy button will issue a JavaScript click on the interactions trigger button, which will trigger whatever interaction you've setup- popup, animation, etc.&#x20;

<img src="../.gitbook/assets/file.excalidraw (1) (1) (1) (1).svg" alt="" class="gitbook-drawing">

## Proxy Trigger Setups

Once you've setup your interactions and click-triggers as described below, you can trigger your named interactions in one of two ways-

### Attribute-Based Trigger&#x20;

You can assign a custom attribute to the button or element you want to use as a trigger, with a value identifying the specific interaction you want to fire.&#x20;

### Link-Based Trigger&#x20;

Or in a link element, we support a special link format.

`##my-interaction-id`

Link anything and set the URL to a double-hash `##` link with the name of the interaction you want to trigger.&#x20;

For example,&#x20;

* `##cta1` can launch your CTA #1 pop-up
* `##enroll` can launch a pop-up form for enrollment&#x20;
* `##llm`, `##ai`, and `##chatgpt` can all be connected to CMS-driven pop-ups to drive a glossary of terms&#x20;
* `##p0543` can display a modal with product or product-category information from your ECommerce store

Because these are set as the link URLs, the test displayed to the user can be anything you like.

## Usage Notes

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Setup your data-binding attributes ( Basic Setup ) <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>

* Create your interaction to do whatever you want
* Create a button element, and set it to trigger your interaction on click
* Assign the `[wfu-ix-id]` attribute to that button element, and give it a unique ID
* Now on any link or button anywhere in your page, you can assign a `[wfu-ix-trigger]` attribute to that element. Give it that same ID to proxy-trigger your interaction.&#x20;
* Or, in any link on your page, assign a URL with `##` with the ID you've assigned to the interaction you want

Now, clicking any of those links will trigger your interactions.&#x20;

### OR/ STEP 2 - Setup your data-binding attributes ( Advanced Setup ) <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>

When you are want CMS-sourced modals such as product pop-ups or glossary pop-ups, here are some tips;

* Design your modal first
* Place it inside of your CMS Collection List
* Place your triggering button as an immediate sibling of your modal's parent element
* In your interaction, trigger the modal _by class_, targeted to _sibling elements only_. That will give much more reliable results&#x20;
* Assign your `[wfu-ix-id]` custom attribute to that button, and set the value using Webflow's CMS data-binding feature, to the `slug` of the collection item

Now, anywhere in your page, you can link to `##slug` to trigger that item.&#x20;

## Specific Setup Examples&#x20;

### You want to click an element, and have a popup appear

* Create your interaction-based popup so that it is triggered by a button. The button can be hidden, but it is needed to invoke the interaction.&#x20;
* Add the `wfu-ix-id` custom attribute to that button&#x20;
* To the triggering element, add the `wfu-ix-trigger` attribute  &#x20;

### You want to click a text link, like a dictionary definition, product, or a staff member's name, and have a link-specific pop-up appear&#x20;

* Create your interaction-based popup so that it is triggered by a button. The button can be hidden, but it is needed to invoke the interaction.&#x20;
* Add the `wfu-ix-id` custom attribute to that button&#x20;
* In your text, create any link you want, and set the link href so that it begins with `##` and then the ID you've assigned to the your modal button&#x20;

You can generate the modals and their triggering buttons from the CMS, and use the slug as the ID.  This makes it easy for you to invoke CMS-generated popups.  &#x20;

## Future <a href="#getting-started-locode" id="getting-started-locode"></a>

### You want an interaction to trigger automatically after N seconds

FUTURE.&#x20;

