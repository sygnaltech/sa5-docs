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

#### `wfu-format-handler` attribute ( required )

Use `wfu-format-handler` directly on the CMS-bound date field.

```
wfu-format-handler = moment
```

{% hint style="info" %}
Currently SA5 uses **momentjs** for date formatting, due to a few features that it offers. It's likely we'll switch to **Luxon** at some point.
{% endhint %}

#### `wfu-format-date` attribute ( required ) <a href="#wfu-format-attribute" id="wfu-format-attribute"></a>

Use `wfu-format-date` directly on the CMS-bound date field.

```
wfu-format-date = (format string)
```

The format string will be the actual formatting string that describes the date & time format you desire. Momentjs supports a wide range of creative formats. Refer to Moment's docs to create the exact formatting string you want;&#x20;

[https://momentjs.com/docs/#/displaying/format/](https://momentjs.com/docs/#/displaying/format/)

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

\
