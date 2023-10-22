---
description: Give your dates the formatting you want
---

# Format Dates ❺

Webflow supports the storage of dates and datetimes in the CMS, with a wide range of formatting options. However it's missing a few and more complex formats require hacks and javascript to achieve a desired result.&#x20;

This library allows you to format your dates and times in a huge range of recognized [formats](https://momentjs.com/docs/#/displaying/format/).

## Demonstration <a href="#usage-notes" id="usage-notes"></a>

{% embed url="https://format-numbers-currency.webflow.io/dates" %}
Demo page
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/format-numbers-currency" %}
Demonstration and Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

{% hint style="info" %}
Webflow offers a range of formats, and you ideally want to choose one that is the most internationally recognizable so that your localization settings do not confuse the parser. The best date format for this is halfway down the list and is shown here.&#x20;
{% endhint %}

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption><p>Ideally use this date format to ensure correct datetime parsing. </p></figcaption></figure>

### `wfu-format-handler` attribute ( optional )

Use `wfu-format-handler` directly on the CMS-bound date field.

```
wfu-format-handler = ( handler )
```

Handler must be one of;

* `day` or `dayjs` to use the DayJS library ( default )
* ~~`moment` or `momentjs` to use the MomentJS library~~

{% hint style="success" %}
Currently SA5 supports **dayjs** for date formatting.&#x20;
{% endhint %}

### `wfu-format-mode` attribute ( optional ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

Use `wfu-format-mode` directly on the CMS-bound date field.

These are the modes;

* `date` ( _default_ ) - Indicates we're formatting the data as-is.&#x20;
* `from` -  Indicates the approximate relative timeperiod between the specified date and today, e.g. "10 months ago," or "in 8 days."
* `to` - Indicates the approximate relative timeperiod between today and the specified date. This is the inverse of `from`.&#x20;
* `age` - Indicates the exact age, in years, between the specified date and today. Designed for past dates, such as birthdates.&#x20;

### `wfu-format-date` attribute ( required ) <a href="#wfu-format-attribute" id="wfu-format-attribute"></a>

Use `wfu-format-date` directly on the CMS-bound date field.

{% hint style="info" %}
This attribute is required, however the value can be blank for `from`, `to`, or `age` modes.&#x20;
{% endhint %}

```
wfu-format-date = (format string)
```

The format string will be the actual formatting string that describes the date & time format you desire. Day.js supports a wide range of creative formats. Refer to their docs to create the exact formatting string you want;&#x20;

Format strings are dependent on the handler. Currently Day.js is the only supported handler.&#x20;

[https://day.js.org/docs/en/display/format](https://day.js.org/docs/en/display/format)

### `wfu-format-suffix` attribute ( optional ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

Use `wfu-format-suffix` directly on the CMS-bound date field. &#x20;

* `on` ( default ) will apply prefix and suffix text such as "in 3 months", or "3 months ago."&#x20;
* `off` will display the raw numeric value only, e.g. "3."&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

\
