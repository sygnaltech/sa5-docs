---
description: Track, store, and apply website state for a better UX.
---

# State ❺🧪

{% hint style="success" %}
**NOT YET AVAILABLE**
{% endhint %}







## Goals

* Arbitrary state definition
* Multi-part storage
  * Ability to store some state items temporarily, others long-term
  * Secure storage options
  * Reporting options
* Apply state
  * Set CSS vars
    * ? Subsets of custom CSS&#x20;
    * ? Add global classes
  * Conditional visibility
  * Set GTM data-layer vars&#x20;
  * Custom JS
    * On-load event handlers&#x20;
    * On-change event handlers, per change type &#x20;
  * Data-binding of state data
    * Bind to hidden form fields for submission&#x20;
* Simple setup&#x20;
  * No need to define a global state object
  * However options to tag state items with specific handling rules
    * Storage, longevity, security&#x20;

Storage & retrieval;&#x20;

* Local;
  * Session storage ( this session, this tab only )
  * Cookie storage ( store for specific duration )&#x20;
  * Local storage ( long term )&#x20;
* Remote;
  * DB, API or KV store
  * Identity system storage
    * User Account vars
    * Memberstack vars

Behavior;

* Smart as to whether state can be preserved long-term
  * i.e. for a var targeted as long-term,&#x20;

## Use Cases

* Light mode / dark mode
* Remembering form data-entry progress for long forms&#x20;
* Sidebar open-closed\
  e.g. [https://discourse.webflow.com/t/enabling-binary-conditions-using-webflow-variables-and-local-storage/270704](https://discourse.webflow.com/t/enabling-binary-conditions-using-webflow-variables-and-local-storage/270704)
* Other UX personalization preferences
* Referral tracking&#x20;
* Shopping cart
* Likes / favorites
* Seen before
* Popup closed&#x20;
* CTA completed&#x20;
  * e.g. email collected, so don't show it again&#x20;
* ? Accessibility states
* Loyalty
  * Points system, for e.g. purchase, actions, repeat visits&#x20;
  * Rewards
* ? Simple points-based e-com





## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../sa5-html/quick-start.md).&#x20;

### STEP 2 - Apply `wfu-decode` to the HTML Embed element you want to decode <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.

\
