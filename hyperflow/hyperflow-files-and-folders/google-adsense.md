---
description: Add Google Adsense to your Webflow site
---

# Google Adsense

[https://www.carbonads.net/](https://www.carbonads.net/)

## What does this do?

Google AdSense requires a special file at `/ads.txt` on your website, which Webflow does not support. Here we add that capability with a worker.

* Serves Google's required `/ads.txt` file, configured as you need
* Config is stored in CF's KV's&#x20;

[https://support.google.com/adsense/answer/12171612?hl=en\&visit\_id=638375256836288617-1363790772\&rd=1](https://support.google.com/adsense/answer/12171612?hl=en\&visit\_id=638375256836288617-1363790772\&rd=1)





## Google Adsense & Others

Google Adsense and other advertising platforms require an `/ads.txt` file for verification.&#x20;

This tool is a standalone worker, and is designed to work with a Cloudflare KV store;

Key: **`HOSTNAME`**`-ads.txt`

Value: Content you want, multiline should work if desired&#x20;

{% hint style="info" %}
HOSTNAME does NOT include www. for consistency. Other subdomains can be used.
{% endhint %}

e.g. key - `sygnal.com-ads.txt`



{% hint style="info" %}
This is done because Workers and KV store is account wide, while you may have multiple sites under it which need varying configurations.
{% endhint %}



Designed for situations like Google Adsense

File is&#x20;

Here's an example; &#x20;

[https://sygnal.com/ads.txt](https://sygnal.com/ads.txt)









## Setup

{% hint style="info" %}
Base domain refers to the "naked domain" with no subdomains, e.g. `foo.com`.  When we refer to base domain, BASEDOMAIN, make certain to use yours.
{% endhint %}

Adsense;&#x20;

* Setup adsense account
* Verify site ownership
* Get the ads.txt snippet\
  e.g. google.com, pub-4476147977893911, DIRECT, f08c47fec0942fa0

Cloudflare;&#x20;

* Add worker path\
  `*brojo.org/ads.txt`\
  Assign to Google Adsense worker
* Add config to ADS\_TXT KV store, e.g. \
  key - `brojo.org-ads.txt`\
  value - the ads.txt snippet

Test it;

Visit your site url with /ads.txt appended&#x20;

[https://www.brojo.org/ads.txt](https://brojo.org/ads.txt)

Adsense;

* Validate&#x20;
* May take days or a week.&#x20;

## Notes

Adsense is kind of cool, you can simply turn on "auto" and let it go nuts with ad placements.

* It places a lot of ads... I've see up to 3 per article, interstitially within the article text.&#x20;
* It places popups that can appear after a few seconds&#x20;
* Content must be good&#x20;









&#x20;

