---
description: About the SA5 Trigger Library
---

# 🔍 About SA5's Trigger Lib

{% hint style="info" %}
This library is being re-conceptualized and is likely to be absorbed into **SA6 Core**.&#x20;
{% endhint %}

SA5's Trigger lib was originally about triggering an interaction such as a pop-up modal from a click event.  The user clicks something and we trigger an interaction event.&#x20;

This was useful for;

* Displaying a modal from a nav button click
* Displaying a pop-up definition when clicking on a linked term in a blog post&#x20;
* Displaying a modal when the user clicks a map pin&#x20;

This concept has expanded significantly, and we're re-conceptualizing everything;

* The types of trigger events we want to support&#x20;
* The resulting actions that we want to support&#x20;
* The model connecting those two&#x20;

## Trigger-Event-Action&#x20;

In the current concept we follow a **Trigger-Event-Action** design;

<img src="../.gitbook/assets/file.excalidraw (1).svg" alt="" class="gitbook-drawing">

Here's the basic mechanic.  Elements in your webpage are marked up with attributes that identify the Triggers and the Event you want fired.&#x20;

Here's an example of a click Trigger, which invokes `my-event`.  &#x20;

```html
<button wfu-trigger-click="my-event">Click me</button> 
```

When a user clicks this button, SA5 invokes the Event named `my-event`.&#x20;

This in turn performs whatever Actions are connected to `my-event`.







* A Trigger fires, e.g. a user clicking on a button&#x20;
* T

These can be arranged in versatile ways;&#x20;

<img src="../.gitbook/assets/file.excalidraw (2).svg" alt="" class="gitbook-drawing">

### Trigger&#x20;

An **SA5 Trigger** is something that occurs, which invokes an _SA5 Event_.  These are generally classified as;

* User triggers.  Click, scroll, hover, etc.&#x20;
* Systems triggers.  Timers, etc.&#x20;
* Webflow triggers. &#x20;
  * Interactions, at any point in the interaction.&#x20;
  * Possibly, certain other system.level mechanics... open or close of a hamburger menu
  * Tab switches
  * Slider events&#x20;
* Custom triggers.  Custom code-triggered events. &#x20;
* Other triggers. &#x20;

### Event&#x20;

An **SA5 Event** is effectively a messaging pipeline, which has a name.  When an event fires, it triggers a series of _SA5 Actions_. &#x20;

* Multiple Triggers can invoke the same Event.&#x20;
* An Event can perform several Actions&#x20;

{% hint style="info" %}
We're considering the ability for a single Trigger to invoke multiple Events. This may be limited to certain trigger types.&#x20;
{% endhint %}

### Action&#x20;

An **SA5 Action** is a resulting action that can be invoked when an SA5 Event occurs.

Examples;

* A click on another element&#x20;
* Navigation
* A webhook call&#x20;
* A logged event&#x20;
* A GTM event&#x20;
* etc.&#x20;

{% hint style="info" %}
We're considering the concept of a Trigger as an Action type, so that we can chain Trigger-Event-Action sequences.&#x20;
{% endhint %}











## Examples&#x20;

Here are some rough examples;

<img src="../.gitbook/assets/file.excalidraw.svg" alt="" class="gitbook-drawing">



## Use Cases&#x20;

This model handles an unthinkable number of possible use cases.

* Mirror click.  Clicking one button clicks another.&#x20;
* Form submit.  Clicking a non-form-submit button triggers a form submission.&#x20;
*













* There may evolve a distinction between Named Events and Unnamed Events
* Named Events can be invoked directly from script&#x20;
*







Concept

Triggers are centralized around the concept of a named event.

A&#x20;



## Considerations

* Need to be mindful of preventing unrestrained circular event firing.&#x20;
* E.g. differentiate between user-triggered and code-triggered clicks  &#x20;











