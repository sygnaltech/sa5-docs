---
description: Fix static URL in Webflow sites to maintain the correct URL
---

# Locale URLs

{% hint style="info" %}
Not yet available publicly.&#x20;
{% endhint %}

## Goals

Fix literal URLs to match the current locale.

In Webflow;

* CMS items cannot link to known pages, you must use a static URL like `/contact`
* Static designer link elements cannot link directly to a CMS item, you must use a static URL like `/blog/awesome-article-23`
* Localization ignores static URLs, including relative urls
* This breaks navigation for users in an alt locale&#x20;

## Features

* Finds specifically tagged links via the `wfu-locale-url` attr
* Determines the current language from the body lang
* Looks up the correct path
* Updates the URL accordingly&#x20;

## Future

Add support for FQDN URLs, e.g. `https://www.thissite.com/some-path`&#x20;

Automatic detection of links ?

Verify functionality on primary domains which are in a `/subdir`

? Auto-determine the list of supported locales and paths

## Usage Notes

I want this link to be locale-fixed.&#x20;

wfu-locale-url = fix







Determine list of locales and paths

Determine current locale from path or lang

Fix path accordingly to match current URL target
