---
description: >-
  Track querystring params and automatically inject them into your forms as
  trackable data.
---

# SA5 Referer Tracking

Track querystring params and automatically inject them into your forms as trackable data.

{% hint style="danger" %}
**UNDER DEVELOPMENT**

Not yet available to the public.&#x20;
{% endhint %}

Key Points;

* We want to track params like UTMs and GCLID's, and pass them into forms&#x20;
* We want this to happen automatically with minimal configuration
* We might want to clear them from the URL so that they are not part of bookmarked content
* We want to temporarily store them so that cross-page navigation can occur safely&#x20;
* Ability to ignore certain querystring patterns;
  * Webflow pagination
  * Specific fields e.g. for FS filters&#x20;
  * or other custom uses&#x20;

Ideally;

* We might want to support forms such as Logic forms&#x20;
  * Smart-add each field. Check for an existing input by that name, if it exists, we apply that value automatically.&#x20;
  * If it doesn't, we auto-create an input type=hidden&#x20;
* We might want to validate some trackers like GCLID's to ensure they are still valid, in case we are visiting from a bookmarked, shared, or published link
* Control over how long data is stored
  * Sessionstorage automatic
  * Localstorage option, for multi-tabbed, or returning users
  * Cookies option, for&#x20;
  * Timeout option, N days&#x20;

Future;

* We might want to track HTTP referer as well
* We might want to track other HTTP headers, e.g. from an app&#x20;
* We might want to track e.g.&#x20;
  * locale&#x20;
  * IP
  * geoip data
  * Webflow page locale
  * User agent type

Possibilities;&#x20;

* We might want to auto-add this to all forms without attributes&#x20;
* We might want to target specific fields&#x20;
* Choose which items are or are not included in a form&#x20;

{% hint style="info" %}
Wait up... isn't it spelled "referrer?"

**"Referrer"**: This is the correct and standard spelling in the English language. It refers to something or someone that refers or directs someone to another source.

**"Referer"**: This is a common misspelling of "referrer." However, it has become standardized in the field of computer science, particularly in internet and web terminology. The term "referer" is used specifically to denote the referring URL in HTTP headers and web logging. This spelling originated from an error in the original HTTP specification (RFC 1945) and has been perpetuated in technical standards and programming ever since.
{% endhint %}

## Usage Notes

### Configuration



```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['trackRefererConfig', 
  (config) => {
    config.fields {
      include = "*",
      exclude = "abc,def",
      excludePagination = true
    };     
    config.forms = "all" | "tagged"; 
    return config;
  }]); 
</script> 
```

## Setup

On&#x20;

wfu-referer-track-fields

(no value) or \* All fields

field1,field-2,field3a

Future;

* Field-level stuff&#x20;

Gclid

[https://support.google.com/analytics/answer/2938246?hl=en#zippy=%2Cin-this-article](https://support.google.com/analytics/answer/2938246?hl=en#zippy=%2Cin-this-article)

