# Usage Notes

* Add the kiosk library, as in quick start
* Add the configuration block&#x20;
* Configure elements on the page to show or hide when in Kiosk Mode&#x20;
* Csutomize your kiosk setup&#x20;



## Goals&#x20;

When in desktop mode;&#x20;

* Hide all kiosk-specific elements&#x20;

When in kiosk mode;&#x20;

* Hide designated elements that are not relevant to kiosk mode&#x20;
* Show designated elements that are kiosk-specific&#x20;
* Make it easy to add custom CSS that can apply only when in kiosk mode&#x20;

## Configuring the Kiosk

_SA5's Kiosk configuration is centralized._ &#x20;

You can paste this into your site-wide code section immediately after the library references, and configure the paramaters the way you want.&#x20;

```html
<script type="application/sa5+json">
{
  "@context": "https://attr.sygnal.com",
  "@type": "KioskConfig",
  "@version": "0.1",
  "homePath": "/kiosk", 
  "userAgent": "KioskApp/1.0", 
  "inactivityTimer": "180"  
}
</script>
```

### Configuration Settings

<table><thead><tr><th width="177">Setting </th><th width="394.3333740234375">Description </th><th>Default</th></tr></thead><tbody><tr><td><code>homePath</code></td><td>Identifies the home page of the kiosk. This is where the kiosk will return to on inactivity reset. </td><td><code>/kiosk</code></td></tr><tr><td><code>userAgent</code></td><td></td><td><code>KioskApp/1.0</code></td></tr><tr><td><code>inactivityTimer</code></td><td>The amount of time during which there is no user activity, before the kiosk will return to its home page. </td><td><code>180</code> ( seconds )</td></tr></tbody></table>

## How it Works&#x20;

{% hint style="warning" %}
At some point, it's likely we'll re-design this to an attributes-based solution, avoiding classes.&#x20;
{% endhint %}

When the page loads, it checks the User Agent to determine if we're in Kiosk mode. That user agent is specifically set in the Kiosk launch script, e.g. `KioskApp/1.0` . &#x20;

When Kiosk mode is detected, these things occur;&#x20;

* A `kiosk`  class is added to the `<body>`  element.&#x20;
* All elements with a class of `kiosk-show`  are displayed&#x20;
* All elements with a class of `kiosk-hide`  are hidden &#x20;

## Configuring Webflow Pages&#x20;

To keep these kiosk-specific sections easily identifiable in the designer, we recommend this approach;&#x20;

* Name your Kiosk classes `--kiosk-hide`  and `--kiosk-show`&#x20;
  * Set both of these to display: none in styles.  These will be made visible by the script depending on the mode determined.&#x20;

{% hint style="info" %}
In Webflow's generated CSS these will be `.kiosk-hide`  and `.kiosk-show` &#x20;
{% endhint %}

* Place these on plain DIV wrappers around the elements you want to affect&#x20;
  * This ensures the classes are visible in the left nav&#x20;
  * It also enables you to easily drag elements in and out of these containers&#x20;

### Custom CSS&#x20;

You can define custom kiosk-mode-only CSS by using the `body.kiosk` selector;&#x20;

```html
<style>
body.kiosk form.lg\:col-span-5 > :nth-child(2) {
  display: none;
}
</style>
```











