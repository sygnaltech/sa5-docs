# Locale-Restricted Content



## Goals

* Allow Webflow designers to easily restrict certain pages or content to certain locales, so that the page or elements simply do not exist when you are in an unsupported locale&#x20;
* Make it easy to admin
* Support locale-restricted CMS items and pages
* Support the sitemap.xml updates
* Support the hreflang updates
* Flexible handling of locale-restricted pages, 404, 301, etc.

## Solution

So far the only solution I've rough-prototyped that I like is this one;

* Reverse proxy, intercepting and modifying all pages
* In Webflow, you add a custom attribute like `avail-langs=en,es,jp` which describes the locales that this page / element is relevant for.
* For restricted pages, you put the attribute on the `<body>` element directly
* For pages/elements that are valid at all locales, you don't need the attribute.

Reverse proxy;

* Checks the `<body>` element for the `avail-langs` attribute. If it exists and the current `lang` is in that list, it returns that page. Otherwise, 404 or redirect, depending on your design goals.
* Updates the `hreflang` alt links so that they only include the correct pages.
* Scans the page for other elements with `avail-langs`. Removes elements where the current `lang` is not in the list given. So, locale-based conditional visibility.

This works quite well because;

* Relatively easy to admin
* Fairly good coverage of the changes required
* Supports locale-restricted pages
* Supports locale-restricted elements
* Works with standard navigation as well
* Works with collection pages and collection lists, by storing that locale list in a text field, and binding it to a custom attribute.

Limitations;

* Without a centralized map of the restricted pages, the sitemap isn't easily fixed, so it will still indicate all locales are available, and will point to some pages that return 404's or redirect somewhere. This means a manually-updated sitemap, or else engineering a separate piece of the reverse proxy.
* Doesn't support ECom products because Webflow's ECom Products collection doesn't support CMS custom attribute binding. However ECom doesn't work with localization anyway yet so this is more of a future issue.
