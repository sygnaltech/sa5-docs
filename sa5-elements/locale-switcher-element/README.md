# Locale Switcher Element ❺🧪

Goals

* Provide for attributes-based locale-switching
* Information access for scripts&#x20;
* ? Conditional-vis based on locale&#x20;

Tech

* Use the locale switcher element, which can be hidden
* Use it to inventory locales, and to switch the locale
  * Useful as it already contains the alt pages for localized links&#x20;

API

* Get Locales List, e.g. en, es, zh, ar
* Get Locales URL's&#x20;
* Identify current Locale
* Switch Locale

Note

* Likely the Locale Switcher does not need to be tagged, but it must exist on the page.  It's already easily identified, and any intact Locale Switcher will work fine as the controller target.&#x20;
*

## Usage Notes

This would be built into Element Actions



`wfu-action` = switchLocale

wfu-action-item = ( locale code )

e.g. `en`&#x20;

wfu-action-trigger = click, always&#x20;

wfu-action-target = unnecessary&#x20;



## Command Line Interface ( CLI )&#x20;

{% hint style="info" %}
**CONCEPTUAL.** We're experimenting with CLI for config support and debugging.&#x20;
{% endhint %}

In the console;

```
sa5.locales
```







### Controller



### Target

The locale switcher

Does not need to be tagged





On elements which&#x20;

### `wfu-action` = ( method ) <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

**Required.** I want my button or link to perform the following action on the targeted deck element.

Method is one of;

* `first` - select the first item
* `prev` - select the previous item
  * ~~`prevLoop`~~ - select the previous item or loop if we're on the first item ( considering )
* `next` - select the next item
  * ~~`nextLoop`~~ - select the next item or loop if we're on the last item ( considering )
* `last` - select the last item
* `goto` - select the specified item, as specified by `wfu-deck-action-item`&#x20;

### `wfu-action-target` = LOCALE-SWITCHER



**Optional.** Specifies the `wfu-tabs`, `wfu-slider` or `wfu-accordion` name you want your action to target.

If unspecified, it will look for the nearest parent deck element as the target. &#x20;

### `wfu-deck-action-item` = ( item number | name )  <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

**Required for the `goto` action only.** Specifies the tab / slide you want to navigate to.&#x20;

* a number - indicates the item number, 1, 2, 3...&#x20;
* a string - activates the item with the specified name&#x20;
