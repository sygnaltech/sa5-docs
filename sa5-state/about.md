---
description: Track, store, and apply website state for a better UX.
---

# 🔍 About SA5's State Lib

{% hint style="info" %}
**CONCEPT STAGE** - gathering requirements and early design strategy&#x20;
{% endhint %}

In many ways, this is an evolution of the SA5 Track library which already performs many of these tasks in a less structured way.&#x20;

The purpose of SA5's State lib is to;

* Maintain a current "state" representation of the website as a JS session object
* Detect changes, like;
  * Clicking a button
  * Submitting a form
  * Visiting a specific page&#x20;
* Store that state ( in various ways, depending on the use case )
  * Retrieve that state later
* Apply the state
  * Conditional visibility
  * Styling changes like light mode / dark mode&#x20;
  * Submit the data with forms&#x20;



