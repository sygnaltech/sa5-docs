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

## Where We're At

In the current concept;

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

An **SA5 Event** is effectively a messaging pipeline, which has a name.  When an event fires, it triggers a series of _SA5 Actions_. &#x20;

* Multiple triggers can fire the same event.&#x20;
*

An **SA5 Action** is a resulting action that can be invoked when an SA5 Event occurs&#x20;

<img src="../.gitbook/assets/file.excalidraw (1).svg" alt="" class="gitbook-drawing">





<img src="../.gitbook/assets/file.excalidraw (2).svg" alt="" class="gitbook-drawing">





## Examples&#x20;

Here are some rough examples;

<img src="../.gitbook/assets/file.excalidraw.svg" alt="" class="gitbook-drawing">





* There may evolve a distinction between Named Events and Unnamed Events
* Named Events can be invoked directly from script&#x20;
*







Concept

Triggers are centralized around the concept of a named event.

A&#x20;





A Trigger invokes an Event which results in Actions.&#x20;

|                                                                                                                                                                                                                                              |                                                                                                |   |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | - |
| <ul><li>A click on an element</li><li>A click on a link</li><li>Mouse over over something</li><li>Scrolling an element into view</li><li>Scrolling to % position on the page</li><li>An interaction occurring, reaching a certain </li></ul> | <ul><li>Fire an interaction</li><li>Click another element</li><li>Navigate to a page</li></ul> |   |
|                                                                                                                                                                                                                                              |                                                                                                |   |
|                                                                                                                                                                                                                                              |                                                                                                |   |



Triggers













