# Copy of What's New?

### v3.35 <a href="#v335" id="v335"></a>

Under development.

### v3.34 <a href="#v334" id="v334"></a>

* Membership
  * Added expand login button

### v3.33 <a href="#v333" id="v333"></a>

* Updates for lightbox captions
  * Suppressed captions on video elements, since they’re ‘Undefined’

### v3.32 <a href="#v332" id="v332"></a>

* Added Webflow Elements
  * Added CMS Lightbox + Captions

### v3.31 <a href="#v331" id="v331"></a>

* Added Webflow Membership module, with conditional element display.

### v3.30 <a href="#v330" id="v330"></a>

* Tracking, added cookies and localStorage options.

### v3.29 <a href="#v329" id="v329"></a>

* Additional numeric formats added to `webflow-format`.

### v3.28 <a href="#v328" id="v328"></a>

* Added user tracking w/ localStorage as `webflow-track`.

### v3.27 <a href="#v327" id="v327"></a>

* Added Decode HTML to `webflow-html`.

### v3.26 <a href="#v326" id="v326"></a>

* Added Hide Section w/ Empty Collection Lists

### v3.25 <a href="#v325" id="v325"></a>

* Added semver sorting.

### v3.24 <a href="#v324" id="v324"></a>

* Upgraded Dynamic attributes.

### v3.23 <a href="#v323" id="v323"></a>

**Lib: `webflow`**

* Added Editor-mode detector.

**Lib: `webflow-html`**

* Added Webflow Editor-mode behavior for nested lists.

### v3.22 <a href="#v322" id="v322"></a>

**Lib: `webflow-html`**

* Sorting expanded to include numeric keys

### v3.21 <a href="#v321" id="v321"></a>

**Lib: `webflow-format`**

* Number formatting for numbers and currency

### v3.20 <a href="#v320" id="v320"></a>

**Lib: `webflow-html`**

* List sorting

### v3.19 <a href="#v319" id="v319"></a>

**Lib: `webflow-commerce`**

* Simple commerce

### v3.18 <a href="#v318" id="v318"></a>

**Lib: `webflow-forms`**

* Added IP Info capture-and-append.

### v3.17 <a href="#v317" id="v317"></a>

**Lib: `webflow-forms`**

* Added ‘n8n’ handler.
* Change handlers so that the form action is retrieve at the point of submit. This way it can be changed live (e.g. for debugging purposes).

### v3.16 <a href="#v316" id="v316"></a>

**Lib: `webflow-forms`**

* Changed `success` handler to `other`.
* Bugfix on form data serilaization.

### v3.15 <a href="#v315" id="v315"></a>

**Lib: `webflow-forms`**

* Redesigned to a webhook-handler approach, which is specified by a `wfu-form-handler` attribute.
* The zapier handler is named `zapier`
* A new `success` handler is added for webhooks that have other JSON response formats.

### v3.14 <a href="#v314" id="v314"></a>

**Lib: `webflow-url`**

* [Automatic targeting of external links](https://wfu.sygnal.com/docs/webflow-url/link-targeting/)
* [CMS relative link fixups](https://wfu.sygnal.com/docs/webflow-url/cms-fixups/)

### v3.13 <a href="#v313" id="v313"></a>

**Dynamic Attributes**

**Breaking Changes**

Attribute name changed from `apply-attr` to `wfu-apply-attr`, e.g.

```
<data type="wfu-apply-attr" apply="prev">
    <data attr="style" value="background-color: yellow;"></data>
</data>
```

**Nested Lists**

**Breaking Changes**

Skeleton loader temporarily disabled, as we work through some issues with Webflow’s editor.

Custom attribute tag is now recommended as `wfu-lists=nested` rather than `wfu-lists=all`.

Both are currently identical, but we will expand on this in the future.
