---
description: Give your dates the formatting you want
---

# Format Dates ❺

Webflow supports the storage of dates and datetimes in the CMS, with a wide range of formatting options. However it's missing a few and more complex formats require hacks and javascript to achieve a desired result.&#x20;

This library allows you to format your dates and times in a huge range of recognized [formats](https://momentjs.com/docs/#/displaying/format/). &#x20;

* Use a format string to explicitly describe the formatting you want.&#x20;
* Supports relative-time phrasing as in "10 months ago" or "in 8 days" using the specified date relative to today.  You can work with past dates, future dates, or use an "age" mode which shows the number of years elapsed since a date.&#x20;
* Automatic localized formatting is supported, based on the `<html lang>` attribute which Webflow Localization uses.&#x20;

## Demonstration <a href="#usage-notes" id="usage-notes"></a>

{% embed url="https://format-numbers-currency.webflow.io/dates" %}
Demo page
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/format-numbers-currency" %}
Demonstration and Cloneable
{% endembed %}

## Getting Started <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Apply the custom attributes <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

SA5's formatting attributes are element-specific.  You simply apply the custom attributes to the date elements you want specially formatted.&#x20;

The details on the attributes are below.&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

{% hint style="info" %}
Webflow offers a range of formats, and you ideally want to choose one that is the most internationally recognizable so that your localization settings do not confuse the parser. The best date format for this is halfway down the list and is shown here.&#x20;
{% endhint %}

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption><p>Ideally use this date format to ensure correct datetime parsing. </p></figcaption></figure>

### `wfu-format-date` = ( format string ) <a href="#wfu-format-attribute" id="wfu-format-attribute"></a>

**Required.**  Place this directly on the element containing your date.

The format strings you can use depends on the configuration settings you have specified, especially `wfu-format-mode`, `wfu-format-handler`, and `wfu-format-locale`.&#x20;

{% hint style="success" %}
We recommend you read through the attributes first to familiarize yourself with them before you jump ahead to the format strings section below.&#x20;
{% endhint %}

{% hint style="warning" %}
**CAUTION** \
Date formats are inherently ambiguous, see Best Practices below for tips on how to ensure your Webflow dates are parsed correctly.&#x20;
{% endhint %}

### `wfu-format-mode` = ( mode ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

**Optional.**  Place directly on the element with the `wfu-format-date` attribute.&#x20;

These are the modes; &#x20;

* `date` ( _default_ ) - Indicates we're formatting the data as a full date.&#x20;
* `from` -  Indicates the approximate relative timeperiod between the specified date and today, e.g. "10 months ago," or "in 8 days."
* `to` - Indicates the approximate relative timeperiod between today and the specified date. This is the inverse of `from`.&#x20;
* `age` - Indicates the exact age, in years, between the specified date and today. Designed for past dates, such as birthdates.&#x20;

{% hint style="info" %}
**FUTURE**\
We're considering use cases for a `rel` relative formatting type which can handle both past and ruture dates and describe them appropriately.&#x20;
{% endhint %}

### `wfu-format-handler` = ( handler )&#x20;

**Optional.**  Place directly on the element with the `wfu-format-date` attribute.&#x20;

Handler must be one of;  &#x20;

* `dayjs` or `day` to use the DayJS library ( default )  &#x20;
* ~~`momentjs` or `moment` to use the MomentJS library~~

{% hint style="info" %}
**Momentjs** support has been deprecated due to the obsolescence of the library.&#x20;
{% endhint %}

### `wfu-format-suffix` = ( enable / disable ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

**Optional.**  Place directly on the element with the `wfu-format-date` attribute.&#x20;

* `on` ( default ) will apply prefix and suffix text such as "in 3 months", or "3 months ago."&#x20;
* `off` will display the raw numeric value only, e.g. "3."&#x20;

{% hint style="warning" %}
This setting works with **modes** of `from`, `to`, and `age`.&#x20;
{% endhint %}

### `wfu-format-locale` = ( no value )&#x20;

**Optional.**  Place directly on the element with the `wfu-format-date` attribute. &#x20;

If specified, the date will be formatted according to the page's current language locale.  This allows your Webflow localized site to have a blog, and to have the dates change depending on which locale the user selects.&#x20;

Locale will be determined by the `<html lang>` attribute in the page, which is automatically set by Webflow Localization when it is correctly configured. &#x20;

* Use with the `dayjs` processor&#x20;
* Use dayjs [localized format strings](https://day.js.org/docs/en/display/format#localized-formats), listed here&#x20;

{% hint style="warning" %}
This settings works with **modes** of `date`. &#x20;
{% endhint %}

## Feature Interoperability&#x20;

SA5 Date Formatting exposes a lot of different options, some of which do not work together;&#x20;

| wfu-format-mode | wfu-format-locale | wfu-format-suffix  |
| --------------- | ----------------- | ------------------ |
| date            | Compatible        | Not applicable     |
| from            | Not yet supported | Compatible         |
| to              | Not yet supported | Compatible         |
| age             | Not yet supported | Compatible         |

## Date Formatting Strings&#x20;

The format string describes the date & time format you desire, and the syntax depends on the **mode** you choose and whether you have localized dates enabled via the **locale** attribute.&#x20;

Here's a breakdown of the different types of format strings you can use;&#x20;

| wfu-format-mode | Non-Localized               | Localized              |
| --------------- | --------------------------- | ---------------------- |
| date            | Standard Date Formats       | Localized Date Formats |
| from            | Time From Now Formats       | n/a                    |
| to              | Time From Now Formats       | n/a                    |
| age             | ( no format string needed ) | n/a                    |

### Standard Date Formats&#x20;

Use when `wfu-format-mode` = `date` and you have not enabled the `wfu-format-locale` attribute.&#x20;

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

### Time From Now Formats&#x20;

Use when `wfu-format-mode` = `from` or `to`.&#x20;

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

### Using Localized Date Formats &#x20;

Use when `wfu-format-mode` = `date` and you _have_ enabled the `wfu-format-locale` attribute.&#x20;

| Format | English Locale            | Sample Output                     |
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

Learn more about Day.js [localized date formats](https://day.js.org/docs/en/display/format#list-of-localized-formats).&#x20;

## Best Practices&#x20;

### Make Your Dates Unambiguous with ISO8601 &#x20;

Date formats are inherently ambiguous, for example M-D-Y and D-M-Y can easily conflict and confuse scripts. To prevent this, we strongly advise that you choose the ISO8601 date format of `YYYY-MM-DD`.&#x20;

In static date fields, you can simply enter your date in that format as in 2025-03-01 = March 1st 2025.&#x20;

In CMS-bound date fields, you can choose this format by clicking the wrench next to the Date field in the right side settings panel.&#x20;

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>









