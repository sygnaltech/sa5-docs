---
description: About the SA5 Trigger Library
---

# 🔍 About SA5's Trigger Lib

{% hint style="warning" %}
DEPRECTING SOON \
This library is being merged into SA5's new [events](../overview/events/ "mention") core functionality.&#x20;
{% endhint %}



{% hint style="success" %}
Much of SA5's most notable developments have been behavioral.  Show or hide items, connect things to the position of a video, perform actions as your slider advances. As a result we've been rethinking how triggers, actions, and events work in SA5.&#x20;

This library is being re-conceptualized and is likely to be absorbed into **SA6 Core**.&#x20;
{% endhint %}

SA5's Trigger lib was originally about triggering an interaction such as a pop-up modal from a click event.  The user clicks something and we trigger an interaction event.&#x20;

This was useful for;

* Displaying a modal from a nav button click
* Displaying a pop-up definition when clicking on a linked term in a blog post&#x20;
* Displaying a modal when the user clicks a map pin&#x20;

## How It's Evolving&#x20;

This concept has expanded significantly, and we're re-conceptualizing everything;

* The types of trigger events we want to support&#x20;
* The resulting actions that we want to support&#x20;
* The model connecting those two&#x20;

At the center of this model is a more versatile structure we refer to as **Trigger-Event-Action ( TEA )**.

This is the simplest TEA arrangement.&#x20;

<img src="../.gitbook/assets/file.excalidraw (1) (1).svg" alt="" class="gitbook-drawing">

Here's the basic mechanic.  Elements in your webpage are marked up with attributes that identify the Triggers, Events, and Actions you want configured.&#x20;

1. A Trigger is fired, such as a button click&#x20;
2. This invokes the specified Event&#x20;
3. The Event then performs the specified Actions&#x20;

Let's look at a simple example;&#x20;

Here's an example of a click Trigger, which invokes `my-event`.  &#x20;

```html
<button wfu-trigger-click="my-event">Click me</button> 
```

When a user clicks this button, SA5 invokes the Event named `my-event`.&#x20;

This in turn performs whatever Actions are connected to `my-event`.

By itself, the above construction does nothing, because the Event is not connected to any Actions.

Let's add an Action to a Webflow tab, so that clicking the button clicks ( and changes to ) that specific tab.&#x20;

Here's an example;&#x20;

```html
<div class="w-tab" wfu-action-click="my-event">Tab 1</div> 
```

When the `my-event` Event is invoked, a click Action will be performed on this tab.&#x20;

In this construction;

* `wfu-action-click` indicates the type of Action that will be performed&#x20;
* `my-event` indicates the Event&#x20;
* The element itself is where the Action will be performed.&#x20;

## More Advanced Eventing&#x20;

The Event is the center of the TEA architecture, and there are two crucial concepts to understand here that grant you a huge amount of flexibility in your designs;&#x20;

* Any number of Triggers can invoke the same Event.&#x20;
* When the Event is invoked, any number of Actions may be performed.&#x20;

<img src="../.gitbook/assets/file.excalidraw (2) (1).svg" alt="" class="gitbook-drawing">

## So Many Types of TEA&#x20;

{% hint style="info" %}
If you're familiar with systems engineering, TEA follows a familiar Pub/Sub style pattern.&#x20;
{% endhint %}

### Triggers&#x20;

Here are a few types of **SA5 Triggers** we're working on, which can invoke _SA5 Events_;&#x20;

* User triggers.  Click, scroll, hover, etc.&#x20;
* Systems triggers.  Timers, etc.&#x20;
* Webflow triggers. &#x20;
  * Interactions, at any point in the interaction.&#x20;
  * Possibly, certain other system.level mechanics... open or close of a hamburger menu
  * Tab switches
  * Slider events&#x20;
* Custom triggers.  Custom code-triggered events. &#x20;
* Breakpoint change triggers.&#x20;
* Keyboard triggers.&#x20;
* Mutation Observer triggers. &#x20;
* Custom triggers. &#x20;
* Other triggers. &#x20;

### Event&#x20;

An **SA5 Event** is effectively a messaging pipeline, which has a name that you assign.  When an event fires, it triggers a series of _SA5 Actions_. &#x20;

* Multiple Triggers can invoke the same Event.&#x20;
* An Event can perform several Actions&#x20;

{% hint style="info" %}
**FUTURE NOTE** \
We're considering the ability for a _single_ Trigger to invoke _multiple_ Events. \
For example, `wfu-trigger-click` = `event1,event2,event3` \
If built, this may be limited to certain trigger types, owever at this point we have not identified key use cases where this adds substantial value.&#x20;
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
**FUTURE NOTE** \
We're also considering the concept of a Trigger as an Action type, so that we can chain Trigger-Event-Action sequences.&#x20;
{% endhint %}







## Examples&#x20;

Here are some rough examples;

<img src="../.gitbook/assets/file.excalidraw (2).svg" alt="" class="gitbook-drawing">



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



## Event Detail&#x20;

{% hint style="info" %}
UNDER CONSIDERATION&#x20;
{% endhint %}

In some scenarios there may be detail or context bundled into the event, which can affect the Action.&#x20;

Considering;&#x20;

* Sub-triggers, such as `##link` items for&#x20;
  * Invoke dictionary pop-ups&#x20;
  * Map pin pop-ups&#x20;
  * Trigger chatbots, with content
  * Trigger AI chatbots ( like Gista ) with a query&#x20;
  * Trigger GTM datalayer and events &#x20;





## Considerations

* Need to be mindful of preventing unrestrained circular event firing.&#x20;
* E.g. differentiate between user-triggered and code-triggered clicks  &#x20;











