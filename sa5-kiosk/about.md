---
description: Add Kiosk Capabilities to your Webflow Site
---

# 🔍 About SA5's Kiosk Lib

{% hint style="warning" %}
**REQUEST FOR COMMENT ( RFC )** \
This SA5 module is currently being defined, and is open for review and comment. \
Use the left-side nav to explore the kiosk section and get an understanding of the kiosk and display mode capabilities we're considering

_Please give feedback in the_ [_SA5 forum_](https://sygnal-attr.discourse.group/)_._&#x20;
{% endhint %}

Webflow websites are typically designed for use in three contexts;&#x20;

* Desktop web browsers
* Tablets
* Mobile phones

However, there are _other usage contexts_ that can be valuable as well.&#x20;

* **Kiosks** - where some or all of the site is available in a touchscreen environment, typically keyboardless, with a tablet-like touch UX. &#x20;
* **Displays** - which present content from the website, using screens, scrolling, audio, and video to both entertain the viewer and inform them about current specials, products, and services.&#x20;

{% hint style="info" %}
For _kiosks_, the _display_ context combines exceptionally well as a special, automatic mode.  When the kiosk is not in use, we can ideally switch to a display mode to engage users and inform them of new products and services, while preventing screen burn-in.&#x20;
{% endhint %}

## Why SA5 Kiosk Exists&#x20;

The purpose of this library is to centralize tooling and best practices that make it easy to create these setups from a Webflow-hosted site;

* Normal public site, with;
  * Kiosk features, including kiosk-only pages and page-variants ( like an ECom Product page ) &#x20;
  * Display features, including content playlists &#x20;
* Kiosk-only site, designed specifically for kiosk use
* Display-only site, designed specifically for hands-free content display&#x20;
* Hybrid sites including all three modes&#x20;

### Features&#x20;

Here are the core capabilities;

* Kiosk mode
  * Kiosk mode detection&#x20;
  * Desktop v. Kiosk-mode conditional visibility&#x20;
* User activity and in-activity detection &#x20;
  * Mode-switching
    * Kiosk inactivity resets to the kiosk homepage, or switches to Display mode&#x20;
    * Kiosk activity leaves display mode and returns to kiosk mode



### Future

The **Display mode** concept has quickly gained value as a worthwhile direction to consider, so plans are to embrace it as an alternative mode in this library as well.&#x20;

## Use Cases

Here are some examples of Kiosk and Display mode for a Webflow site being used in real world situations. &#x20;



|                                                            | Display                                                                                  | Kiosk                                                                                          |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Real estate                                                | Window display showing current property listings from the website.                       | In-reception kiosk for browsing and searching available properties and booking showing times.  |
| Restaurant                                                 | Window display, or at couter display show food, cooking videos, menu items and specials. | Ordering                                                                                       |
| Dental office                                              | Showcase treatments and self care. Educate, and get questions about                      | Interactive learning about specialized treatments a client might be interested in.             |
| Tattoo parlor, hair salon, makeup salon ( lashes, nails )  | Showcase designs. Educate clients on options.                                            | Browse catalog                                                                                 |
| SPCA                                                       | Pets for adoption                                                                        | Browse pets for adoption, ven across centers                                                   |
| Retail shop                                                | Specials, new products, featured products, commercials                                   | Ordering products, browsing products, searching products                                       |





## Kiosks

* Kiosks - where some or all of the site is available in a touchscreen environment, typically keyboardless, with a tablet-like touch UX.  Used in a retail outlet or waiting room
* Displays - which present content, and change it&#x20;
* Hybrid - a kiosk which, when not in use, falls into a display mode state&#x20;

And Still others

* Watch









