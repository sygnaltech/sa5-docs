---
description: Give an image a 3D-like depth, and a parallax-like mouseover effect
---

# Depthmap (Fake 3D) Image ❺🧪

<figure><img src="../.gitbook/assets/2024-06-11_11-47-00.gif" alt=""><figcaption><p>A low-framerate capture of the effect in action</p></figcaption></figure>

_\*\* Much smoother in real use._&#x20;



## Usage Notes

### Media Prep

[https://tools3ox.com/tools/images/dmapgen/](https://tools3ox.com/tools/images/dmapgen/)



On the image element;

`wfu-effect` = `depthmap`



Inventory all attributes on the element, look for wfu-effect-setting-\*&#x20;

Unknown setting error&#x20;

Based on Interface?&#x20;

Pull that value into a settings object

Pass it to



wfu-effect-setting-map = ( url )

wfu-effect-setting-xthreshold = ( integer )

Defaults to 20

wfu-effect-setting-ythreshold= ( integer )

Defaults to 20









### Add the SA5 Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../sa5-modals/quick-start.md).&#x20;



{% hint style="info" %}
Docs not yet written.&#x20;
{% endhint %}





### I want this element to represent my suppressible content

To the outermost element you want to suppress;

* Add a custom attribute of `wfu-modal` = ( name ). Give it any custom name you like. That name will be used in the suppression tracking so you can e.g. have the same modal on every page, and suppress it site-wide.
* Add a custom attribute of `wfu-modal-trigger` = `load`.&#x20;
* Add the suppression duration you want, using `wfu-modal-suppress-days` = ( days ). If unspecified, defaults to about 1 year.&#x20;

### I want this element to be the close button

To the close element(s) within the modal;

* Add an attribute of `wfu-modal-close` = `true`
* Add an attribute of `wfu-modal-close-type` = `auto`

## Questions? Feature Requests?

Visit the SA5 forum link at the top of this page.

