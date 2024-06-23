# Webflow Modals ❺🧪

{% hint style="danger" %}
**PROTOTYPING**\
Not yet available to the public&#x20;
{% endhint %}

## Goals

Near term;

* Content source
  * Define any DIV in your design as modal content, and make it possible to easily open a modal
    * Div can be visible or hidden
  * External URL such as a booking URL, in an IFRAME&#x20;
* Auto scroll content if needed ( not for IFRAME? )&#x20;
* Styling
  * Customizable scrollbar
  * Customizable modal - background color, rounded corners, border, padding
    * Possible min size and max size, or breakpoint-specific sizing&#x20;
    * Max-height&#x20;
  * Adjust overlay opacity, color, etc
  * Animation on open and close&#x20;
  * Default classes applied
    * Option for a suffix to make a specific modal more specific
* Trigger modal display via
  * Attribute name
  * Attribute URL
  * Custom code
    * Internal SA5 Booking lib, composing a URL and then triggering the modal&#x20;
* Restrict to a single modal open at a time
  * Auto close any prior modal if a new modal is open
  * ? Allow override of the single-modal rule ?&#x20;
* Built-in suppression

Medium term;

* Other page content on site, easily accessible for centralized modals
* CMS-driven modal content
  * e.g. dictionary definitions
* Trigger capability using SA5's `##link` standard capability&#x20;
* GTM Integration&#x20;
* Trigger modal via
  * Form submission
    * All validation checks confirmed, but we want an I agree on the privacy policy or cancellation terms, etc.&#x20;
    * Login / sign-up / password page&#x20;
    * Automatic on site visitation? I am over 18?&#x20;

Long-term;

* Off-site content

## Use Cases

* Display a cancellation policy section on your page
  * Then invoke it in other places on your page as a scrollable modal
    * E.g. in your booking form at the bottom, a reminder about the cancellation policy&#x20;
* Invoke an external resource such as a booking form

## Usage Notes ( Modal Setup )

Create your DIV containing your modal content, and apply the attributes below, depending on the configuration and behavior you choose;&#x20;

### I want this DIV to be usable as content for a modal

`wfu-modal` = ( name )

Give your modal a unique name, which can be referenced.

{% hint style="info" %}
Any DIV you apply the `wfu-modal` attribute to is referred to as a **modal element**, for the configuration docs below.&#x20;
{% endhint %}

{% hint style="info" %}
You can use a CMS-bound value such as a slug for the name. Just ensure it is also unique from any other modals on the page to prevent naming conflicts.&#x20;
{% endhint %}

{% hint style="info" %}
**FUTURE.** \
wfu-modal-zone or groups, to namespace CMS-bound modals, and site-wide modals
{% endhint %}

### I want this URL to be loaded in an IFRAME, as a named modal

This would be added on a **modal element** which is otherwise _empty_.  Any existing content will be deleted.

`wfu-modal-content-url` = ( url )

* A relative path wi

Things to consider;

* Interactions, scripts, etc.&#x20;

## Usage Notes ( Modal Trigger Setup )

{% hint style="info" %}
Some triggers, like timer and exit-intent triggers are defined on the modal directly. Others are defined on separate elements such as button elements.&#x20;
{% endhint %}

SA5 supports both manual triggers automatic triggers. &#x20;

* Manual triggers are intentionally invoked by the user as part of the user flow, and will be invoked even if the user repeats that flow multiple times.
* Automatic triggers occur outside of the user action, and should not occur again if the modal has already been invoked ( manually or automatically ). &#x20;

<table><thead><tr><th width="110">Trigger</th><th>Notes</th><th>Type</th></tr></thead><tbody><tr><td>button</td><td>Triggers the modal when the user clicks on a button or other element that is tagged. </td><td>manual</td></tr><tr><td><del>form</del></td><td>Triggers the modal when the user submits a form.</td><td>manual</td></tr><tr><td>timer</td><td>Triggers the modal when a timer has elapsed, starting from page load.</td><td>auto</td></tr><tr><td>scroll</td><td>Triggers the modal when the page has been scrolled x%.</td><td>auto</td></tr><tr><td>scrollintoview</td><td>Triggers the modal when a certain element is scrolled into view.</td><td>auto</td></tr><tr><td>exit</td><td>Triggers the modal on exit intent.</td><td>auto</td></tr></tbody></table>

{% hint style="info" %}
Multiple triggers can be applied to the same modal, for example, two button triggers, a timer, and a scroll trigger can all invoke the same modal. To support this, the attributes for each trigger type are discrete ( see below ).&#x20;
{% endhint %}

? Consider trigger once rule&#x20;

### I want my modal to automatically trigger on a timer

On the modal element itself, add this attribute;&#x20;

`wfu-modal-trigger-timer` = ( wait duration )

Duration is specified in SA5's duration format, which is an integer followed by an optional unit of measurement, as follows;

<table><thead><tr><th width="160">Suffix</th><th width="175">Unit </th><th>Examples</th></tr></thead><tbody><tr><td><code>ms</code> ( default )</td><td>Milliseconds</td><td><code>10000ms</code> = 10 seconds<br><code>10000</code> = 10 seconds</td></tr><tr><td><code>s</code></td><td>Seconds</td><td><code>30s</code> = 30 seconds</td></tr><tr><td><code>m</code></td><td>Minutes</td><td><code>20m</code> = 20 minutes</td></tr><tr><td><code>h</code></td><td>Hours</td><td>4h = 4 hours</td></tr><tr><td><code>d</code></td><td>Days</td><td><code>3d</code> = 3 days</td></tr><tr><td><code>w</code></td><td>Weeks</td><td><code>1w</code> = 1 week</td></tr><tr><td><code>M</code></td><td>Months</td><td><code>2M</code> = 2 months ( at 30 days per month )</td></tr><tr><td><code>y</code></td><td>Years</td><td><code>2y</code> = 2 years ( at 365 days per year )</td></tr></tbody></table>

### I want my modal to automatically trigger on an exit intent

This refers to the mouse leaving the browser window, which is thought to be leaving the site. &#x20;

? Change this to on close or on navigation?&#x20;

On the modal element itself, add this attribute;&#x20;

`wfu-modal-trigger-exit` = ( no value needed )&#x20;

### I want my modal to automatically trigger on page scroll

Trigger the modal when the page scrolls a certain distance from the top, or a percentage of the total page height.&#x20;

On the modal element itself, add this attribute;&#x20;

`wfu-modal-trigger-scrollpage` = ( px | percentage )&#x20;

{% hint style="info" %}
For a more precise scroll trigger, see the scroll into view trigger. &#x20;
{% endhint %}

### I want this button or element to trigger my modal on click

On the button or element to be clicked, add this attribute;

`wfu-modal-trigger-click` = ( modal-name )

Specify the modal's name.&#x20;

`wfu-modal-trigger-action` = ( `open` | `close` | ~~`toggle`~~ )

( optional ). `open` is the default setting. &#x20;

{% hint style="info" %}
The purpose of this setup is to allow you to open a modal or close a modal from any element on your page.&#x20;
{% endhint %}

### I want my modal to trigger when this element is scrolled into view

On scroll into view;

? will hidden elements work, or only zero size elements&#x20;

`wfu-modal-trigger-scrollintoview` = ( modal-name )





## Future&#x20;



( modal-name ) | ( zone.modal-name )

**name** will target the first modal found with that name in the page.

**zone.name** will target the first modal found with that zone and name in the page

`wfu-modal-target-zone` = ( zone )

This is a convenience to separate the zone from the name. It's most oftenly used when the name is bound to a CMS slug, and the one needs to group those items separately from other modals in the page.&#x20;

### Modal appearance options

Scroll freeze option&#x20;

Sound FX&#x20;

### Buttons? &#x20;

For OK close separate from e.g. hyperlinks or other actions

Cancel?&#x20;

Allow user to create these, or we default add a button?&#x20;

Lets us separate content from popup

modal-button

modal-button-class

### Support for Forms

wfu

### Callback

On OK, Cancel&#x20;

## Common Configurations

### Setup content for a modal, trigger with a button



### Setup content for a modal, make it auto-trigger on page upen



### Form modal, e.g. accept terms&#x20;



### Over 21 Gate&#x20;



