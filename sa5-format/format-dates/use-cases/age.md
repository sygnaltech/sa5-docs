---
description: SA5 Format Dates.  Quick setup for the most popular use cases.
---

# Age

Indicates the exact age, in years, between the specified date and today. Designed for past dates, such as birthdates.&#x20;

## Getting Started&#x20;

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../quick-start.md).

### STEP 2 - Apply the custom attributes <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

SA5's formatting attributes are element-specific.  You simply apply the custom attributes to the date elements you want specially formatted.&#x20;

The details on the attributes are below. &#x20;

## Usage Notes &#x20;

Place these attributes directly on element with the date or date-time value you want to format. These can be static strings, or CMS-bound.&#x20;

{% hint style="success" %}
For best results, format the string using Webflow's `YYYY-MM-DD` format option, to ensure the best parsing for Day.js scripts.&#x20;
{% endhint %}

### `wfu-format-mode` = `age`&#x20;

**Required.**  Specifies the mode as _age_ display. &#x20;

### `wfu-format-date` = ( _no value needed_ )&#x20;

**Required.**  However the string itself is not used in this mode. &#x20;

### `wfu-format-suffix` = ( enable / disable ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

**Optional.**  Place directly on the element with the `wfu-format-date` attribute.&#x20;

* `on` ( default ) will apply prefix and suffix text such as "in 3 months", or "3 months ago."&#x20;
* `off` will display the raw numeric value only, e.g. "3."&#x20;

### Notes

These attributes are _not needed_, as the default value is appropriate for this use case;&#x20;

* `wfu-format-mode` = `date`&#x20;
* `wfu-format-handler` = `dayjs`&#x20;

These attributes are incompatible;&#x20;

* `wfu-format-locale`&#x20;















