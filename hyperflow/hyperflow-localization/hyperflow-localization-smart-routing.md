# Hyperflow Localization Smart-Routing

Webflow's Localization offers auto-routing on the advanced localization plan however it has some problems;

* Pricing, for many, is out of reach as it more than doubles the cost per-locale, for all locales&#x20;
* It cannot differentiate between locales, i.e. it uses language only. This means that if you have e.g. en-US, and en-GB, it will force all English browsers to one of these.
  * This appears to happen even when the user explicitly selects a locale from the dropdown

### The Locale-Determination Problem

* The problem may be that WF does not check the locale and match appropriately
* It may also be that many browsers do not identify a specific locale and my simply identify themselves as `en`.&#x20;

### Hyperflow Solution

Solutions;

* Check the browser for locale
* If only language is specified, attempt to further determine locale on the basis of location&#x20;
  * as determined by GeoIP
* Log this, for stats
* Determine available locales
  * By config? manifest? other?&#x20;
* Identify best match
* Route accordingly, if needed

If user changes locale via locale switcher;

* Remember full locale, and utilize

If user arrives on a specific localed page;

* Set this as the preferred locale&#x20;
* Capture stats?&#x20;
*

### Ingredients

Map, containing;

* All supported locales
  * May include both `en` and `en-GB` forms.&#x20;
* Related path&#x20;
* Identification of default locale&#x20;
  * May or may not have a prefix&#x20;
* Ability to determine alt paths
  * LINKs altlang&#x20;
    * Cache in KV map table based on default locale path?&#x20;
    * Reset on rebuild?&#x20;

Preferred locale storage;&#x20;

* Localstorage? But with a supported localed map version. If map is updated, update date, will reject localstorage data as outdated.&#x20;

## Process Diagram

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Functional detail;&#x20;

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

