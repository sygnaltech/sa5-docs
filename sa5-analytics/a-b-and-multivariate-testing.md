# A/B and Multivariate Testing

{% hint style="info" %}
CONCEPTUAL
{% endhint %}

Goals;

* Fully integrated MVT
* Ability to trigger code, interactions, and show/hide elements
* Ability to scope MVT Experiments to pages, path parts, or tagged elements, so that multiple experiments can be run independently and simultaneously&#x20;
* All data capture in a 3rd party package like GA4&#x20;

Design;&#x20;

* Experiment manager ( external? )
* Experiment scope, i.e. by page or defined by zones using a custom attribute
* Auto-applies Experiment data and variant data to existing GTM data blocks
  * So that cross-impact can be ascertained.&#x20;
* Experiment engine
  * Show/hide
  * Various triggers e.g. IX2&#x20;
  *

