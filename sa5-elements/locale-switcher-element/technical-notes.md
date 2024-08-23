---
description: Technical Notes regarding the Webflow Locale Switcher
---

# Technical Notes

This is a locales list;&#x20;

* `.w-locales-list`
  * `.w-locales-items`
    * `w-locales-item`
      * `a[hreflang]`  = locale code&#x20;

If the link is the current locale, it will have a class of `.w--current`&#x20;

Navigating to the link `href` generally appears to be the same as clicking it ( no obvious cookies or background scripts in Localization Lite, but there may be in Pro )&#x20;

The link Text is generally the name of the Locale.&#x20;

```html
<div class="w-locales-list">
    <div role="list" class="locales-list-3 w-locales-items">
        <div role="listitem" class="locale-2 w-locales-item">
            <a hreflang="en" href="/test/locale" aria-current="page" class="w--current">English</a>
        </div>
        <div role="listitem" class="locale-2 w-locales-item">
            <a hreflang="es" href="/es/test/locale">Spanish</a>
        </div>
        <div role="listitem" class="locale-2 w-locales-item">
            <a hreflang="zh" href="/zh/test/locale">Chinese</a>
        </div>
        <div role="listitem" class="locale-2 w-locales-item">
            <a hreflang="ar" href="/ar/test/locale">Arabic (Standard)</a>
        </div>
    </div>
</div>
```

