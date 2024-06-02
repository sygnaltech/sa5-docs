---
description: Add a fractional 5-star rating element to your site
---

# 5-Star Ratings Component ❺

{% hint style="success" %}
Likely to move this into Elements.&#x20;
{% endhint %}

## Overview

Generate CMS-compatible 5-star ratings on your site using a simple HTML embed and a dynamic custom attribute;

```html
<div wfu-ui="rating" wfu-rating="5.0"></div>
```

## Examples

See here for a [demonstration](https://wfu.sygnal.com/docs/webflow-ui/ratings/).

View source to see the specifics on how these demos work.

```html
<div wfu-ui="rating" wfu-rating="5.0"></div>
```

```html
<div wfu-ui="rating" wfu-rating="1.5"></div>
```

```html
<div wfu-ui="rating" wfu-rating="3.5"></div>
```

```html
<div wfu-ui="rating" wfu-rating="3.5" style="width: 200px;"></div>
```

### Coloring <a href="#coloring" id="coloring"></a>

Since the art is SVG-based, it can affected by the CSS `fill` attribute.

However, Webflow does not directly provide access to the fill attribute, or SVG’s. Best practice is to put a `<style>` element or CSS in the `<head>` however most browsers will accept an in-body `<style>` element.

```html
<style>
#stars2 svg {
    fill: red; 
}
</style>
```

{% hint style="info" %}
Due to the way the shaded area works, the color and darkness is not easily specified.
{% endhint %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

* The rating stars are SVG, so the component will scale to whatever width you define in the designer.
* You can use fractional amounts. Generally, .0 or .5 display nicely, other fractions may show too little of the star edges to be clearly understood.
* The DIV HTML is generally embedded in a Webflow EMBED element, so that the `wfu-rating` attribute can be easily set from a CMS Collection List.
* Apply a class to the EMBED with a width and minimum height in order to make the Embed visible in the designer.
* You can put temporary contents in the Embedded DIV for designer display, this will be wiped.

## Getting Started ( NOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

There are currently no configuration options for the data-binding feature, so we’ll use a _no-code_ integration approach.

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../sa5-url/quick-start.md).

### STEP 2 - Create an EMBED where you want a WFU Rating component to appear. <a href="#step-2---create-an-embed-where-you-want-a-wfu-rating-component-to-appear" id="step-2---create-an-embed-where-you-want-a-wfu-rating-component-to-appear"></a>

Paste this code into the EMBED;

{% code overflow="wrap" %}
```html
<div wfu-ui="rating" wfu-rating="3.5">
    RATING
</div>
```
{% endcode %}

Alternatively, you can put anything into the DIV and it will be deleted when the Rating Component is created. In this way, you can have a visible placeholder while you’re in the designer, where scripts cannot run.

We recommend placing stars there for convenience. If you are using this with Webflow, you can place an **HTML Embed** element inside of your div, with the following contents, to create visible stars.

```html
<div wfu-ui="rating" wfu-rating="3.5">
    <svg viewBox="0 0 576 512" width="20%" title="star">
        <path d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z" />
    </svg><svg viewBox="0 0 576 512" width="20%" title="star">
        <path d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z" />
    </svg><svg viewBox="0 0 576 512" width="20%" title="star">
        <path d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z" />
    </svg><svg viewBox="0 0 576 512" width="20%" title="star">
        <path d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z" />
    </svg><svg viewBox="0 0 576 512" width="20%" title="star">
        <path d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z" />
    </svg>
</div>
```

### STEP 3 - Create a Class on the Embed <a href="#step-3---create-a-class-on-the-embed" id="step-3---create-a-class-on-the-embed"></a>

In the Webflow designer, add a class to the embed.

Set the width of the embed to whatever you want- the SVG stars will scale.

Set a min-height of 20px, to ensure the element is visible at design time, for layout purposes.

### STEP 4 - Configure the rating value <a href="#step-4---configure-the-rating-value" id="step-4---configure-the-rating-value"></a>

Set the `wfu-rating` attribute of the div to whatever value you want, between 0.0 and 5.0.

{% hint style="info" %}
You can make the rating a fixed value, however generally, you’d place this in a Collection List, and bind the attribute to a Rating field from the Collection.
{% endhint %}

Here's how to set that up;

* Use a numeric field named e.g. `Rating`
* Configure the field’s minimum to 0, maximum to 5, with precision 1.0. A precision of 1 is fine if you will not be using fractional ratings like 3.5.
* Set the field to required, if you will always have a rating. If you won’t always have a rating, leave it as not required, and configure the Embed element so that it is conditionally visible and hidden in no-rating situations.



\
