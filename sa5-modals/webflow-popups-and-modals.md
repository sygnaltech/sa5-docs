---
description: Easily create and manage popups and modals in your Webflow projects.
---

# Webflow Popups & Modals ❺🧪

{% hint style="danger" %}
**BETA TESTING** \
Drop a message in the forum if you'd like to join the beta team.&#x20;
{% endhint %}

In Webflow, building popups and modals has several challenges;

* Editing them is not designer-friendly&#x20;
* There is no suppression feature to allow snoozing
* Triggers are limited
* They're very reliant on interactions
* Behaviors are difficult to control, e.g. close only if terms are accepted&#x20;

SA5's provides a Webflow-centric JS-based modal solution that resolves all of these issues.&#x20;

## Popups v. Modals

_What's the difference?_&#x20;

In SA5 docs we generally use the term "modals" to refer to either, but there are some important UX distinctions we want to preserve.

* **Popups** generally contain non-critical information, and can be easily dismissed. Typical uses;
  * Special offers
  * Notices like holiday hours
  * Newsletter subscription forms&#x20;
* **Modals** generally contain critical information, and require specific user action to dismiss them.&#x20;
  * Accept terms to proceed, like an over 18 gate&#x20;
  * Gated content. Enter your email to continue reading the article

Initially Sygnal's focus will be on popup UX support, and we'll extend this to include modal behavior support as customer needs demand.&#x20;

{% hint style="info" %}
GDPR & cookie acceptance has its own special requirements, so we do not plan to build those types of capabilities into SA5 modals.&#x20;
{% endhint %}

## Roadmap

| Feature                             | Short Term                                                                                                        | Medium Term                                                                                                                                                                                                                                    | Future                                                                                                                                                                   |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Modal setup in the Webflow designer | 2 DIVs                                                                                                            | Possibly only 1 DIV, with auto-frame generation                                                                                                                                                                                                |                                                                                                                                                                          |
| Modal type                          | <ul><li>Popup. Easily closed.</li></ul>                                                                           | <ul><li>Modal. Only a specific action can close. </li></ul>                                                                                                                                                                                    |                                                                                                                                                                          |
| Content source                      | <ul><li>Static content</li></ul>                                                                                  | <ul><li><p>CMS content</p><ul><li>Named with zones</li></ul></li></ul>                                                                                                                                                                         | <ul><li>IFRAME</li><li>External source e.g. Google Doc</li></ul>                                                                                                         |
| Modal frame styling                 | <ul><li>Borders</li><li>Corners</li><li>Padding</li><li>Shadows</li><li>Background</li><li>Transparency</li></ul> | <ul><li>Possible themes</li></ul>                                                                                                                                                                                                              |                                                                                                                                                                          |
| Content admin                       | <ul><li>Designer</li><li>Content editor</li></ul>                                                                 |                                                                                                                                                                                                                                                |                                                                                                                                                                          |
| Triggers ( open )                   | <ul><li>Trigger element click</li></ul>                                                                           | <ul><li>Timed trigger</li><li>Trigger element scroll-into-view</li><li>Page scroll to %</li><li>Exit intent</li><li>Link triggers using SA5's <code>##link</code> standard capability </li></ul>                                               | <ul><li><p>JS</p><ul><li>SA5 booking lib</li></ul></li><li>Cookie exist / not-exist</li><li>URL formation e.g. <code>#book</code> </li><li>Adblocker detection</li></ul> |
| Triggers ( close )                  | <ul><li>Close button ( auto )</li><li>Close button ( manual )</li><li>External close trigger click</li></ul>      | <ul><li>Timer</li><li>ESC key</li><li><p>Successful form submission</p><ul><li>Delay? thanks... close</li></ul></li></ul>                                                                                                                      | <ul><li>% Page scrolling?</li><li>Programmatic triggers, like an over 18 that checks birthdate calc </li></ul>                                                           |
| Suppression                         | Defined at the modal level                                                                                        | <ul><li>Possibly add sessionStorage as a suppression mechanism</li><li>Form submit suppression on success only</li></ul>                                                                                                                       | <ul><li>Possibly button-specific suppression ( for "never show again" )</li></ul>                                                                                        |
| Scrolling                           | Manually defined at the modal level via custom CSS chunk                                                          | <ul><li>Attribute with basic scrolling behaviors</li><li><p>Basic scrollbar style attributes</p><ul><li>thin-black</li></ul></li></ul>                                                                                                         |                                                                                                                                                                          |
| Sizing                              | <ul><li>Defined at the modal frame level, responsively</li><li>Min size, max size</li></ul>                       |                                                                                                                                                                                                                                                |                                                                                                                                                                          |
| Positioning                         | Centered                                                                                                          | 9 positions                                                                                                                                                                                                                                    |                                                                                                                                                                          |
| Animation on open / close           | Simple predefined                                                                                                 | <ul><li>slide in/out + direction</li><li>grow/shrink</li><li>fade in/ out</li></ul>                                                                                                                                                            | <ul><li>WF Interactions</li></ul>                                                                                                                                        |
| Overlay                             | <ul><li>Simple predefined styling</li><li>Click triggers close</li></ul>                                          | <ul><li><p>Themes</p><ul><li>gray</li><li>glass</li><li>blur</li></ul></li></ul>                                                                                                                                                               | <ul><li>Customizable ( as an element? )</li><li>Ability to suppress click on close</li></ul>                                                                             |
| Timing                              | <ul><li>None</li></ul>                                                                                            | <ul><li><p>Schedule</p><ul><li>Start / end dates</li><li>Weekdays</li><li>Hours of the day</li></ul></li></ul>                                                                                                                                 | <ul><li>Allow invocation override by a trigger to force show outside of scheduled times</li></ul>                                                                        |
| Competition                         | <ul><li>None? </li></ul>                                                                                          | <ul><li>Restrict to a single modal open at a time</li><li>Auto close any prior modal if a new modal is open</li><li>Modal queue?  Show sequentially. </li><li><p>Prioritization</p><ul><li>High</li><li>Medium</li><li>Low</li></ul></li></ul> | <ul><li>Non-critical v. critical- auto suppress non-critical if another has shown</li></ul>                                                                              |
| Page behavior                       | <ul><li>None</li></ul>                                                                                            | <ul><li>Support no-scroll on page content behind the modal</li></ul>                                                                                                                                                                           | <ul><li>Support scrolling as a trigger to close the modal</li></ul>                                                                                                      |
| Analytics                           | <ul><li>None</li></ul>                                                                                            | <ul><li>GTM</li></ul>                                                                                                                                                                                                                          |                                                                                                                                                                          |

## Use Cases

* Display a cancellation policy section on your page
  * Then invoke it in other places on your page as a scrollable modal
    * E.g. in your booking form at the bottom, a reminder about the cancellation policy&#x20;
* Invoke an external resource such as a booking form
* Prevent progress without acceptance?
  * Form submission
    * All validation checks confirmed, but we want an I agree on the privacy policy or cancellation terms, etc.&#x20;
    * Login / sign-up / password page&#x20;
    * Automatic on site visitation? I am over 18?&#x20;
  * I agree...&#x20;
* Content gating?&#x20;
  * Login or email
* Email / lead capture&#x20;
* Anti-Adblocker

## Modal Structure

A modal typically has 4 identifiable parts;&#x20;

* **Modal frame.** The outer frame of the modal, which dictates the frame styling ( corners, border, shadow ) sizing and padding. This is the center of the modal and defines most settings of the modal.&#x20;
* **Modal content.** The content of the modal. Dictates any scrolling and scrollbar behavior of the content area itself.&#x20;
* **Close button** ( optional ). Will be auto-generated if unspecified
* **Overlay** ( automatic ). The background that covers the page to make the modal more visible.&#x20;
* **Sidebar** ( optional ). Used to provide visual artwork that is distinct from the scrollable content area.&#x20;

```
DIV wfu-modal = ( name )
  DIV wfu-modal-button = close ( optional )
  DIV wfu-modal-sidebar ( optional )
  DIV wfu-modal-content 
    .. modal content
```

* The `wfu-modal` DIV is required, it defines and names the modal.&#x20;
* The `wfu-modal-content` is optional, but important to controlling content scrolling.&#x20;
* The `wfu-modal-sidebar` is optional. Does it need an attribute? &#x20;
* The `wfu-modal-button` is optional. It will be auto-created as an X if it does not exist&#x20;



hiding the modal in the designer

hiding the modal on load

closin

## Advanced Notes

### Multi-Function Modals

Buttons which perform an action and also close the modal?&#x20;

* Submit an email form&#x20;
* Accept terms
* Confirm 18, etc.&#x20;

### Open / Close Animations

* default show
* grow from a point
* slide in right
* slide in left
* slide in bottom
* slide in top
* spin in right
* fade in
* random, or a list of random CSV options

## Usage Notes ( Modal Setup )

Create your DIV containing your modal content, and apply the attributes below, depending on the configuration and behavior you choose;&#x20;

### I want this DIV to define a modal

`wfu-modal` = ( name )

Give your modal a unique name, like `modal-1`. Use standard identifier conventions, e.g. avoid spaces. We recommend names that use only lowercase letters, hyphens, and numbers.&#x20;

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

### Define the type ( future )&#x20;

* `popup` ( default ) - means the modal can be easily closed
* ~~`modal`~~

Primarily this setting affects the default for various modal properties;&#x20;

{% hint style="info" %}
These distinctions and the behaviors they affect are under development, these names will likely change.&#x20;
{% endhint %}

| Behavior                                  | popup                     | modal                                |
| ----------------------------------------- | ------------------------- | ------------------------------------ |
| <p>Close button<br>wfu-close-button</p>   | auto - Auto-created       | none - Not auto-created close button |
| <p>Click overlay<br>wfu-overlay-click</p> | close - Closes the modal  | none - Does nothing                  |
| <p>Page scrolling<br>wfu-page-scroll</p>  | allow - Scroll by default | prevent - No scroll by default       |

### Hide the modal content

Needed?&#x20;

`wfu-modal-state` = `hidden`

Place this on the same element as you have the `wfu-modal` attribute on.  This ensures the modal is not visible when the page initially opens. &#x20;

Test with new structure?&#x20;

{% hint style="info" %}
**DESIGNER PRO TIP**\
If you want to hide the modal content at design time, we recommend placing it at the bottom of the page, and then marking the modal element itself as&#x20;

wrapping the modal in a DIV, which you mark as display: none.  This will allow you to easily hide/show the modal in the designer to work on it.&#x20;
{% endhint %}

### Close Button

wfu-modal-close-button = auto&#x20;

* `auto` will create a close button if one is not already created in this modal&#x20;
* `none` means no close button, clicking the overlay is used for closing&#x20;
  * Also used for modal mode?  type =&#x20;

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

<table><thead><tr><th width="167">Trigger</th><th width="465">Notes</th><th>Type</th></tr></thead><tbody><tr><td>button</td><td>Triggers the modal when the user clicks on a button or other element that is tagged. </td><td>manual</td></tr><tr><td><del>form</del></td><td>Triggers the modal when the user submits a form.</td><td>manual</td></tr><tr><td>timer</td><td>Triggers the modal when a timer has elapsed, starting from page load.</td><td>auto</td></tr><tr><td>scroll</td><td>Triggers the modal when the page has been scrolled x%.</td><td>auto</td></tr><tr><td>scrollintoview</td><td>Triggers the modal when a certain element is scrolled into view.</td><td>auto</td></tr><tr><td>exit</td><td>Triggers the modal on exit intent.</td><td>auto</td></tr></tbody></table>

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



## Pro Tips

### Style Guide Page

Making modals accessible and editable is important, and one of the best ways to do this is to use a Style Guide page.&#x20;

{% hint style="info" %}
It's common to make Style Guide pages draft, so that they are not published as part of the site and do not appear in SERPs- however this (??) makes them difficult to access in the Content editor (verify??).  Instead, you can password protect them.&#x20;
{% endhint %}



Create a&#x20;

If you are tur

* Put your entire modal including the frame in a component, hidden&#x20;
* Put that comp

If your clients use the Content Editor, rather than the designer, you can make the modal accessible to them by;

* Create a Style-guide folder
  * Password protect it
* In it, create pages for the main stylistic elements of your site, e.g. Blog page, Modals, etc.&#x20;
* Drop your modal components on the modals page&#x20;

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



