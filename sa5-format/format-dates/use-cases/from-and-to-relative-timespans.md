---
description: SA5 Format Dates.  Quick setup for the most popular use cases.
---

# From and To Relative Timespans

From and To modes display an approximate relative timeperiod between the specified date and today, e.g. "10 months ago," or "in 8 days."&#x20;

## Getting Started&#x20;

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../quick-start.md).

### STEP 2 - Apply the custom attributes <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

SA5's formatting attributes are element-specific.  You simply apply the custom attributes to the date elements you want specially formatted.&#x20;

The details on the attributes are below.&#x20;

## Usage Notes &#x20;

Place these attributes directly on element with the date or date-time value you want to format. These can be static strings, or CMS-bound.&#x20;

{% hint style="success" %}
For best results, format the string using Webflow's `YYYY-MM-DD` format option, to ensure the best parsing for Day.js scripts.&#x20;
{% endhint %}

### `wfu-format-mode` = ( _mode_ )&#x20;

**Required.**  Here, valid values for mode are;&#x20;

* `from` - indicates Time from Now&#x20;
* `to` - indicates Time to Now &#x20;

{% hint style="success" %}
Almost always, you will want to use `from` here.  To inverts the time range which has very few practical use cases.&#x20;
{% endhint %}

### `wfu-format-date` = ( _format string_ )&#x20;

**Required.**  Create your format string using any of the [Format Strings](from-and-to-relative-timespans.md#format-strings) below.  &#x20;

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

## Format Strings &#x20;

SA5 supports both pre-defined fully-formatted localized dates, and custom format strings.&#x20;

### Time From Now Formats&#x20;

| Range                    | Key | Sample Output                    |
| ------------------------ | --- | -------------------------------- |
| 0 to 44 seconds          | s   | a few seconds ago                |
| 45 to 89 seconds         | m   | a minute ago                     |
| 90 seconds to 44 minutes | mm  | 2 minutes ago ... 44 minutes ago |
| 45 to 89 minutes         | h   | an hour ago                      |
| 90 minutes to 21 hours   | hh  | 2 hours ago ... 21 hours ago     |
| 22 to 35 hours           | d   | a day ago                        |
| 36 hours to 25 days      | dd  | 2 days ago ... 25 days ago       |
| 26 to 45 days            | M   | a month ago                      |
| 46 days to 10 months     | MM  | 2 months ago ... 10 months ago   |
| 11 months to 17months    | y   | a year ago                       |
| 18 months+               | yy  | 2 years ago ... 20 years ago     |

[https://day.js.org/docs/en/display/from-now](https://day.js.org/docs/en/display/from-now)

















