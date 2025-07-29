# Future Attributes

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

## Close Options

* Close button
* Close clicking canvas
* Require button click ( modal )&#x20;
* Successful form submit





### I want this URL to be loaded in an IFRAME, as a named modal

This would be added on a **modal element** which is otherwise _empty_.  Any existing content will be deleted.

`wfu-modal-content-url` = ( url )

* A relative path wi

Things to consider;

* Interactions, scripts, etc.&#x20;

### ~~I want my modal to automatically trigger on a timer~~

On the modal element itself, add this attribute;&#x20;

`wfu-modal-trigger-timer` = ( wait duration )

Duration is specified in SA5's duration format, which is an integer followed by an optional unit of measurement, as follows;

[Durations](../../../overview/durations.md)&#x20;







### Freeze Page Scrolling

Prevent scrolling of the page while the modal is open.&#x20;

### ~~I want my modal to automatically trigger on an exit intent~~

This refers to the mouse leaving the browser window, which is thought to be leaving the site. &#x20;

? Change this to on close or on navigation?&#x20;

On the modal element itself, add this attribute;&#x20;

`wfu-modal-trigger-exit` = ( no value needed )&#x20;

### ~~I want my modal to automatically trigger on page scroll~~

Trigger the modal when the page scrolls a certain distance from the top, or a percentage of the total page height.&#x20;

On the modal element itself, add this attribute;&#x20;

`wfu-modal-trigger-scrollpage` = ( px | percentage )&#x20;

{% hint style="info" %}
For a more precise scroll trigger, see the scroll into view trigger. &#x20;
{% endhint %}

### I want my modal to trigger when this element is scrolled into view

On scroll into view;

? will hidden elements work, or only zero size elements&#x20;

`wfu-modal-trigger-scrollintoview` = ( modal-name )

## wfu-modal-trigger-click

`wfu-modal-trigger-action` = ( `open` | `close` | ~~`toggle`~~ )

**Optional.** If specified, it determines the action that occurs.

? Can be used with any trigger type?  Scroll etc.&#x20;

* `open` ( default )&#x20;
* `close`
* `toggle`

{% hint style="info" %}
The purpose of this setup is to allow you to open a modal or close a modal from any element on your page.&#x20;
{% endhint %}





