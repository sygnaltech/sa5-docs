# Viewport META

## Goals

* Fix inconsistencies in certain newer mobile devices where the webpage is rendered as too narrow or is clipped on the right side. Seen most recently in Chrome on iPhone 14 Pro and iPhone X.&#x20;

## The Problem

Webflow generates the following viewport META, which cannot be configured.

`<meta content="width=device-width, initial-scale=1" name="viewport" />`

Some modern devices don't handle it well and you end up with an oddly scaled view;&#x20;

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Solutions

In initial testing this revised viewport META seems to work with modern iPhones ( early 2024 ).&#x20;

{% code overflow="wrap" %}
```html
<meta content="width=device-width, initial-scale=1.0, minimum-scale=1.0" name="viewport" />
```
{% endcode %}

However there are many other options you can use as well for your specific use case-&#x20;

{% code overflow="wrap" %}
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no">
```
{% endcode %}

### Options-

#### Duplicate the Tag

Duplicate the tag and hope browsers choose ours. This is done by simply pasting our revised META into the site-wide page HEAD code area. This seems to be working in most cases in my tests.

#### Use Javascript

Use Javascript to modify Webflow’s, which might or might not get picked up as a change by mobile browsers, and applied.

_Untested._

Something like...

{% code title="" overflow="wrap" %}
```javascript
// Find the viewport meta tag
var viewportMetaTag = document.querySelector('meta[name="viewport"]');

// Modify the content attribute of the viewport meta tag
viewportMetaTag.setAttribute('content', 'width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no');
```
{% endcode %}

#### Reverse-Proxy&#x20;

Reverse proxy the site, and fix Webflow’s tag to what we want before the browser receives it.&#x20;

{% hint style="success" %}
Sygnal's Hyperflow framework provides this capability.&#x20;
{% endhint %}
