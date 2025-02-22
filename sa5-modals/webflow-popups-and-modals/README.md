---
description: Easily create and manage popups and modals in your Webflow projects.
---

# Webflow Popups & Modals

{% hint style="info" %}
**BETA RELEASE**\
SA5 Modals is fully available, but attributes and features may change in the final release. \
&#xNAN;_&#x44;rop a message in the forum if you'd like to join the beta team._&#x20;
{% endhint %}

In Webflow, building popups and modals has several challenges;

* Editing them is not designer-friendly&#x20;
* There is no suppression feature to allow snoozing
* Triggers are limited
* They're very reliant on interactions
* Behaviors are difficult to control, e.g. close only if terms are accepted&#x20;

SA5's provides a Webflow-centric JS-based modal solution that resolves all of these issues.&#x20;

## Demonstration

{% embed url="https://sa5-modals.webflow.io/modals" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/sa5-modals" %}
Cloneable
{% endembed %}

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
* **Modal content** ( optional )**.** The content of the modal. Dictates any scrolling and scrollbar behavior of the content area itself.&#x20;
* **Close button** ( optional ). Will be auto-generated if unspecified
* **Overlay** ( automatic ). The background that covers the page to make the modal more visible.&#x20;
* **Sidebar** ( optional ). Used to provide visual artwork that is distinct from the scrollable content area.

In your HTML DOM the structure is arranged like this;&#x20;

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

## Modal Lifecycle

SA5 Modals are designed to be flexible, but there is a typical lifecycle;

* Closed ( pending ).  This is generally the initial state of a modal for a new user visiting the site, it is not suppressed, but it is also initially hidden.&#x20;
* Open.  Some trigger has occurred like click, timer, scroll, exit intent, which open the modal.&#x20;
  * When the user closes it, it can be configured to suppress so that it won't auto-open again for e.g. 3 days&#x20;
* Closed ( suppressed ).  It's closed and a natural trigger such as a timer won't re-open it.&#x20;

Here's a state diagram;&#x20;

<img src="../../.gitbook/assets/file.excalidraw (4).svg" alt="" class="gitbook-drawing">



In a typical setup there is a lifecycle;&#x20;

* Closed ( pending )
* Opened, by trigger ( user button click, timer trigger, scroll to position, etc&#x20;
* Closed ( suppressed )&#x20;

In some situations, you may also want to be able to re-open the modal, which can be allowed by user click even when the modal is suppressed to automatic triggers &#x20;









## Usage Notes ( Modal Setup )

Create your DIV containing your modal content, and apply the attributes below, depending on the configuration and behavior you choose;&#x20;

### I want this DIV to define a modal

`wfu-modal` = ( name )

Give your modal a unique name, like `modal-1`. This will be used in places like your modal trigger buttons.&#x20;

{% hint style="info" %}
Use standard identifier conventions, e.g. avoid spaces. We recommend names that use only lowercase letters, hyphens, and numbers.&#x20;
{% endhint %}

{% hint style="info" %}
Any DIV you apply the `wfu-modal` attribute to is referred to as a **modal element**, for the configuration docs below.&#x20;
{% endhint %}

{% hint style="info" %}
You can use a CMS-bound value such as a slug for the name. Just ensure it is also unique from any other modals on the page to prevent naming conflicts.&#x20;
{% endhint %}

## Usage Notes ( Modal Trigger Setup )

### I want this button or element to trigger my modal on click

On the button or element to be clicked, add this attribute;

`wfu-modal-trigger-click` = ( modal-name )

Specify the modal's name. &#x20;

### I want the modal to appear after X milliseconds

Triggers the modal when a timer has elapsed, starting from page load.&#x20;

Place this directly on the modal element.&#x20;

`wfu-modal-trigger-timer` = ( time in milliseconds )

{% hint style="info" %}
1 second = 1,000 ms, so if you want to wait 5 seconds, set the value to `5000`.
{% endhint %}

## Usage Notes ( Modal Suppression Setup )

After a modal is closed, we will likely want to suppress it for some period of time.

`wfu-modal-suppress` = ( suppression setting )

* `forever` - suppresses indefinitely
* `session` - suppresses only for the duration of the webstorage session
* FUTURE - we'll add specific durations

Note that the suppression is handled using a cookie-based or web-storage-based suppression key which includes the name of the modal.  If you ever change the name of the modal, and republish your site, any existing suppression keys would be ignored.&#x20;

{% hint style="success" %}
The defined suppression state on the modal is applied immediately after the modal is opened. This ensures that it is honored regardless of how the modal is closed- including a CTA button navigation within the modal.&#x20;
{% endhint %}



