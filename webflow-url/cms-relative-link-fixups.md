# CMS Relative Link Fixups

{% embed url="https://wfu.sygnal.com/docs/webflow-url/cms-fixups/" %}

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Webflow’s CMS feature has a significant limitation in that the CMS knows nothing about its containing site.

As a result of this design gap, it’s currently not possible to link from a CMS collection item to a known page in your site, in the same way you can link within the designer.

CMS’s have a Link field type, however a second limitation prevents the use of relative paths, which means you cannot even link to e.g. /about/.

How to use;

* In any CMS where you want a relative link to a site page, simply place that link in a CMS link field, with `https://self/` as the protocol and hostname.
  * e.g. to link to `/about`, you’d write it as `https://self/about`.

The link fixup library will find and correct this link to a proper relative link of `/about`.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Install JS in BODY, site-wide or on the specific pages you want the script to affect.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/nocode/webflow-url.min.js"></script>
```
{% endcode %}

#### STEP 2 - Create CMS Links as desired <a href="#step-2---create-cms-links-as-desired" id="step-2---create-cms-links-as-desired"></a>

See above notes.

\
