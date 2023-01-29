# URL Query Params Passthrough

{% embed url="https://wfu.sygnal.com/docs/webflow-url/query/" %}

**NO-CODE. Designed for Webflow.**

Extract querystring parameters from your URL, and apply the contents to tagged elements on your page.

* Use querystring data in your FORM data, to collect it for submissions ( e.g. `utm_` params )
* Pass querystring data through to other links on the page, so it will get carried through
* Use querystring data in visible fields, e.g. to personalize a page from an Email newsletter link click ( “Hey Mary!” )

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Configure everything using simple custom attributes.

This tool will carry any URL querystring params into your webpage, and apply them as follows;

* On any INPUT elements with a custom attribute of `wfu-query-param=X`, WFU will replace the `value` attribute with the value of the querystring param `X`. This works with `type=hidden` INPUT elements as well, so the data can be passed through invisibly.
* On any other elements with a custom attribute of `wfu-query-param=X`, WFU will replace the inner text of the element with the value of the querystring param `X`.
* For **all** links on your page, WFU will modify the link’s `href`, depending on what you request.
  * `wfu-query-param=*`, or an absence of the `wfu-query-param` attribute, will merge all params from the page’s current URL into the link href.
  * `wfu-query-param=foo,bar,bat`, will only merge the querystring params named `foo`, `bar`, and `bat` from the page’s current URL into the link href.
  * `wfu-query-param=-` (a hypen) will suppress processing of this link, and no changes will be made.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this script to the `</body>` custom code area, either site-wide or on the specific pages you want the script to affect.

```
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/src/nocode/webflow-url.js"></script>
```

#### STEP 2 - Apply `wfu-query-param` to Desired Elements <a href="#step-2---apply-wfu-query-param-to-desired-elements" id="step-2---apply-wfu-query-param-to-desired-elements"></a>

_For example, use `wfu-query-param=X` if you want to apply the value of param `X` to that element._

Applied to form INPUT elements, it will display the value in side the textbox.

To create a hidden form INPUT element, create it in your FORM as an HTML Embed element, containing the HTML `<input>` element code, e.g.;

```
<input wfu-query-param="test2" type="hidden" name="test2-field">
```

Applied to any other elements, the inner text of the element will be replaced with the value of the param.

All `<a>` links on the page will automatically be affected. You do not need the custom attribute on them, unless you’re wanting to specify which params are merged in.

The processing of a specific link can be suppressed by applying the `wfu-query-param` custom attribute with a hyphen (`-`) as the value.

_Note that this will be expanded on eventually with configuration options, and the ability to merge querystrings._

\
