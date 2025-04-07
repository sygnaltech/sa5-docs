---
description: Best Practices for your date field settings.
---

# Setup Your Date Field for Good Parsing

This module is built on top of day.js, which is the recognized standard for JS date-time formatting. It parses your current date content automatically, and handles the formatting, date math, and localization as well.&#x20;

Unfortunately dates are not globally standard- a common example is month-day-year vs. day-month-year conventions that different countries have.&#x20;

{% hint style="warning" %}
Does 01-03-2025 mean Jan 3rd, or March 1st?  _It depends on where you are._&#x20;
{% endhint %}

## Best Practices&#x20;

To ensure that day.js is parsing the date correctly, the best practice is to use an international convention close to ISO8601. &#x20;

{% hint style="success" %}
ISO8601 uses a YMD convention, e.g. 2025-03-01, which will always be able to parse as March 1st, 2025.&#x20;
{% endhint %}

We highly recommend that you use this convention to ensure good parsing.&#x20;

For CMS-stored dates, Webflow offers a range of formats.  The best date format for this is halfway down the list and is shown here.&#x20;

Use either...

* YYYY-MM-DD HH:mm&#x20;
* or YYYY-MM-DD&#x20;

{% hint style="success" %}
The first option works for all uses you might have.  The second works if you do not care about the time portion.&#x20;
{% endhint %}

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption><p>Ideally use this date format to ensure correct datetime parsing. </p></figcaption></figure>









