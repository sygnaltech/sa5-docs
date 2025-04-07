---
description: SA5 Format Dates.  Quick setup for the most popular use cases.
---

# Localize a Date

SA5 Format supports Webflow Localization and can automatically localize of dates depending on the current locale the user has selected.&#x20;

For custom date or datetime formatting, use this configuration.&#x20;

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

### `wfu-format-date` = ( _format string_ )&#x20;

Create your format string using any of the [Standard Date Formats](localize-a-date.md#standard-date-formats)  &#x20;

### `wfu-format-locale` = ( _no value_ )&#x20;

### Notes

These attributes are _not needed_, as the default value is appropriate for this use case;&#x20;

* `wfu-format-mode` = `date`&#x20;
* `wfu-format-handler` = `dayjs`&#x20;

## Format Strings &#x20;

SA5 supports both pre-defined fully-formatted localized dates, and custom format strings.&#x20;

### Pre-Defined Localized Date Formats &#x20;

These pre-defined formats have the advantage of adjusting the ordering of the data time parts for the locale. For example, `L` would display m/d/y in the US, and d/m/y in Europe.&#x20;

| Format | English Locale            | Sample Output ( EN )              |
| ------ | ------------------------- | --------------------------------- |
| `LT`   | h:mm A                    | 8:02 PM                           |
| `LTS`  | h:mm:ss A                 | 8:02:18 PM                        |
| `L`    | MM/DD/YYYY                | 08/16/2018                        |
| `LL`   | MMMM D, YYYY              | August 16, 2018                   |
| `LLL`  | MMMM D, YYYY h:mm A       | August 16, 2018 8:02 PM           |
| `LLLL` | dddd, MMMM D, YYYY h:mm A | Thursday, August 16, 2018 8:02 PM |
| `l`    | M/D/YYYY                  | 8/16/2018                         |
| `ll`   | MMM D, YYYY               | Aug 16, 2018                      |
| `lll`  | MMM D, YYYY h:mm A        | Aug 16, 2018 8:02 PM              |
| `llll` | ddd, MMM D, YYYY h:mm A   | Thu, Aug 16, 2018 8:02 PM         |

Learn more about Day.js [localized date formats](https://day.js.org/docs/en/display/format#list-of-localized-formats). &#x20;

### Custom Date Formats&#x20;

From light experimentation, day.js localization works well with custom string parts as well.&#x20;

Combine these format parts into a format string you want;&#x20;

|        |                  |                                       |
| ------ | ---------------- | ------------------------------------- |
| Format | Output           | Description                           |
| `YY`   | 18               | Two-digit year                        |
| `YYYY` | 2018             | Four-digit year                       |
| `M`    | 1-12             | The month, beginning at 1             |
| `MM`   | 01-12            | The month, 2-digits                   |
| `MMM`  | Jan-Dec          | The abbreviated month name            |
| `MMMM` | January-December | The full month name                   |
| `D`    | 1-31             | The day of the month                  |
| `DD`   | 01-31            | The day of the month, 2-digits        |
| `d`    | 0-6              | The day of the week, with Sunday as 0 |
| `dd`   | Su-Sa            | The min name of the day of the week   |
| `ddd`  | Sun-Sat          | The short name of the day of the week |
| `dddd` | Sunday-Saturday  | The name of the day of the week       |
| `H`    | 0-23             | The hour                              |
| `HH`   | 00-23            | The hour, 2-digits                    |
| `h`    | 1-12             | The hour, 12-hour clock               |
| `hh`   | 01-12            | The hour, 12-hour clock, 2-digits     |
| `m`    | 0-59             | The minute                            |
| `mm`   | 00-59            | The minute, 2-digits                  |
| `s`    | 0-59             | The second                            |
| `ss`   | 00-59            | The second, 2-digits                  |
| `SSS`  | 000-999          | The millisecond, 3-digits             |
| `Z`    | +05:00           | The offset from UTC, ±HH:mm           |
| `ZZ`   | +0500            | The offset from UTC, ±HHmm            |
| `A`    | AM PM            |                                       |
| `a`    | am pm            |                                       |

See the full docs- \
[https://day.js.org/docs/en/display/format](https://day.js.org/docs/en/display/format)













