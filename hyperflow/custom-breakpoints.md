---
description: Redesign Webflow's CSS file for custom breakpoints
---

# Custom Breakpoints

**Webflow offers 7 breakpoints for design.**

From largest to smallest, they are;

* 1920px >= 1920px
* 1440px >= 1440px
* 1280px >= 1280px
* Desktop (base) from 992px to 1279px
* Tablet <= 991px
* Mobile landscape <= 727px
* Mobile portrait <= 478px

```
// Some code
// Webflow breakpoints
const breakpoints = {
  large1920: '(min-width: 1920px)',
  large1440: '(min-width: 1440px) and (max-width: 1919px)',
  large1280: '(min-width: 1280px) and (max-width: 1439px)',
  desktop: '(min-width: 992px) and (max-width: 1279px)',
  tablet: '(min-width: 768px) and (max-width: 991px)',
  mobileLandscape: '(min-width: 480px) and (max-width: 767px)',
  mobilePortrait: '(max-width: 479px)'
};
```

&#x20;? Internal name

&#x20;? Interactions&#x20;

By default, the [largest 3 breakpoints](https://webflow.com/blog/3-new-larger-breakpoints-in-webflow) only exist if you add them, or if you are using a template that has added them.

Remember also how breakpoints work-

> Desktop (base): styles apply to all devices unless overridden at other device breakpoints

Which is essential for understanding layout and styling techniques.

[https://university.webflow.com/lesson/intro-to-breakpoints](https://university.webflow.com/lesson/intro-to-breakpoints)

Goals

* Fix bug relating to one of the boundaries, as default&#x20;
* Rewrite all @media min-width and max-width settings with custom breakpoints
* Also store the breakpoints as CSS vars for custom CSS use&#x20;

Notes;

* &#x20;Requires un-minified CSS? Test.&#x20;

CONFIG

```
// Some code
{
  "desktop": "1279px",
  "tablet": "1100px",
  "landscape": "800px"
}
```

Initializes a range of&#x20;

```
// Some code
@media screen and (max-width: 479px) {
@media screen and (max-width: 767px) {
@media (min-width: 768px) {
@media screen and (max-width: 991px) {
@media screen and (min-width: 1280px) {
@media screen and (min-width: 1440px) {
@media screen and (min-width: 1920px) {
```

[https://assets.sygnal.com/59b8d49f7fdf9700017d780f/css/sygnal.6442ac1d6.css](https://assets.sygnal.com/59b8d49f7fdf9700017d780f/css/sygnal.6442ac1d6.css)

\
In CSS, you cannot directly store the `min-width` media query in a CSS variable, as media queries are not part of the CSS property-value system and thus cannot be assigned to variables. However, you can store the width value itself in a CSS variable and use it in various places, but the media query syntax itself will need to be written out each time.

```
// Some code
:root {
    --min-screen-width: 1440px;
}

/* but you still need to use the regular media query syntax */
@media screen and (min-width: 1440px) {
    /* styles */
}

```



