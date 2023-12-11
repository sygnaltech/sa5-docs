---
description: >-
  Track querystring params and automatically inject them into your forms as
  trackable data.
---

# SA5 Referer Tracking ❺🧪

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

## Discussions and Setup

\[quote="Kev99, post:3, topic:263427"] Pretty LInks is a company that’s for Word Press where you can shorten affiliate links/cloak, track clicks in detail, etc. Doesn’t sound like there is a third-party tool for Webflow from other companies yet. \[/quote]

If you don't find a packaged solution, these are easy to build. Typically on Webflow I run with;

* Wildcard redirect from e.g. `/link/(.*)` -> `/track?link=%1` to consolidate shortlink requests.
* Script to lookup the affiliate code from CMS data, add a cookie\*\*, and redirect to the target page
* I have a global script which injects a hidden field into all forms containing the affiliate code automatically just to keep things simple
* I also inject that code into the GTM data layer, so that any GTM conversion events like button clicks also have that data.

\*\* Depending on your marketing policy, you can set that cookie expiry to match how long that affiliate click is considered valid.

\[quote="Kev99, post:3, topic:263427"] Google Analytics and Tag manager don’t offer the same flexibility and tracking as Pretty Links. \[/quote]

I'm finding that hard to imagine ;) but what they do lack is simplicity. Massively over-engineered for basic stats tracking.

Also you can make the entire system completely transparent ( no redirects ) using a reverse proxy to deliver the page directly via a rewrite.

You should be able to adapt this approach for any stats-tracking platform, but in most cases we use the form submit data directly ( it goes into Salesforce / Pipedrive / Nutshell etc. ), or we're just after the conversion data which GTM feeds to Analytics.

##

##

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

