---
description: Restrict access to content with an SA5 gate
---

# Gating Modals

**SA5 Gating Modals** are the same as a regular modal, but they are automatically invoked when the user attempts to perform specific actions, like;

* Click a link or button&#x20;
  * This would usually navigate to a new page, or open the link content in a new window&#x20;
* Click an SA5 Modal click trigger element &#x20;
  * This would usually open an SA5 Modal&#x20;

An SA5 Gating Modal setup "interrupts" these user actions and displays a special modal to complete a designated action first.&#x20;

Depending on your configuration the user must do one of three things to open the gate, and proceed to the link or modal content they've requested.&#x20;

1. Simply view the gating modal.  Once it's dismissed, the gate is open and the action proceeds.&#x20;
2. Click a specific button in the gating modal. When clicked, the action proceeds.&#x20;
3. Complete and submit a form.  When the validated form is submitted, the action proceeds.&#x20;

{% hint style="success" %}
**SA5 Gating Modals** are specially designed so that they only need to appear once per device.  Once the gating modal's requirements are satified, the gate is opened and the user does not need to repeat the gating action.  &#x20;

_This is true even if the gate is used on different pages throughout the site._&#x20;
{% endhint %}

The flow looks like this;&#x20;

<img src="../../.gitbook/assets/file.excalidraw (6).svg" alt="" class="gitbook-drawing">

## Use Cases&#x20;

* Present important information&#x20;
  * e.g. a cancellation policy&#x20;
* Ensure user agreement, where the user must click a button to proceed&#x20;
  * e.g. "I am over 18"&#x20;
  * e.g. "I agree to receive investment advice" &#x20;
* Collect information successfully from a form &#x20;
  * e.g. basic contact info for a sales process&#x20;
  * e.g. user info before giving a reward&#x20;

{% hint style="warning" %}
**SECURITY NOTE** \
SA5 Modals are a marketing and policy convenience- they do not provide direct content security.  Anyone with the basic knowledge on how to view your page's code can see and access gated links and content.&#x20;
{% endhint %}

## Usage Notes &#x20;

Depending on how the gated modal is configured, it will require different actions to _pass_ the gate and continue to the requested content. &#x20;

### `wfu-modal-gate` = ( _name_ )&#x20;

**Required.**  Indicates that a specific link or modal click trigger element is gated. Must specify the name of the `wfu-modal` to to use as the gate.   &#x20;

Its behavior depends on the type of element it is placed on which must be one of;&#x20;

| Element Type                                   | Behavior                                                                                           |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| SA5 Modal, containing the `wfu-modal` element  | Gates the modal with a pre-modal.  Used when you are giving content, but want a gate before that.  |
| Link, Link Block, or Button element            | Gates the link. Once the gate is passed, the link is navigated.                                    |
| ~~Body element~~ 🧪                            | ~~Gates the page. Covers the page with a "blur" and a modal state that.~~                          |

## Usage Notes - Gate Completion

Once the Gating Modal appears, there are a few ways to configure the completion options.&#x20;

{% hint style="info" %}
SA5 Modal still have normal "pop-up" style behavior, in which they can easily be closed by the user.  However if the user does not perform the required gate action, the gate will not be "opened" and the requested action will not be performed.&#x20;
{% endhint %}

### View the Gating Modal&#x20;

If you just want the user to see the modal once, and then dismiss it normally ( click close, click on the overlay, etc. ) then use this attribute;&#x20;

`wfu-modal-gate-view` = ( no value needed ) &#x20;

{% hint style="info" %}
Add this attribute directly to the gating modal's modal element.&#x20;
{% endhint %}

### Button Click Required&#x20;

If a button must be clicked to complete the gate successfully, use;&#x20;

`wfu-modal-gate-button` = ( no value needed )&#x20;

{% hint style="info" %}
Add this attribute to one or more buttons.&#x20;

These buttons must be within the Gating Modal.   The modal will be automatically closed on button click, before the next action is performed.&#x20;
{% endhint %}

### Form Submission Required&#x20;

If a form must be successfully submitted to complete the gate successfully, add;&#x20;

`wfu-modal-gate-form` = ( no value needed )&#x20;

{% hint style="info" %}
Add this attribute to that Form element directly ( not the form wrapper element ).&#x20;

This form must be within the Gating Modal. The form submission must be successful in order to complete the gate.  The modal will be automatically closed on successful form submission, before the next action is performed.&#x20;
{% endhint %}

<img src="../../.gitbook/assets/file.excalidraw (5).svg" alt="" class="gitbook-drawing">

## Technical Notes

All gating is currently tracked as localStorage.&#x20;

## Future&#x20;

Future goals include e.g. partial page gating, like show a part of an article, prevent scrolling, and then undo that once the gate is opened.&#x20;

### Suppression Options&#x20;

* Forever - LocalStorage&#x20;
* Temporary - SessionStorage&#x20;
* Timed - Cookie&#x20;

Must be on the modal used for gating.&#x20;

### Function Gate  &#x20;

* `func` - call a function to determine gate passage  &#x20;

{% hint style="info" %}
Func could be used for e.g. calculate age from date of birth in a form, and confirm. &#x20;
{% endhint %}

### SA5 Trigger&#x20;

Considering how this works with SA5 Trigger. &#x20;

## Where Gating Can be Implemented&#x20;

* Links... put the gate directly on a link or button.  User must complete the modal gate, and is then redirected to the requested content.&#x20;
  * Support \_target&#x20;
* Page access?  Hide page content first&#x20;
* Partial page gating? &#x20;
* Gating another SA5 modal&#x20;
  * Modal 1 is requested
  * Modal 2 then intervenes&#x20;
* Form Submit
  * A final gate is presented before the form submission can occur, e.g. a cancellation policy&#x20;















