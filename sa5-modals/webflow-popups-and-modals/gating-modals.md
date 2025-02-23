---
description: Restrict access to content with an SA5 gate
---

# Gating Modals 🧪



{% hint style="warning" %}
**SECURITY NOTE** \
SA5 Modals are a marketing and policy convenience, that presents users with a modal that they do not provide content security in a direct fashion.  Anyone wh
{% endhint %}

## Use Cases

* Age gating ( simple confirmation )&#x20;
* Terms of Use, e.g. Securities site&#x20;
* Fill-in a form and submit successfully&#x20;

Not supported...

* Fully secure content from access, including page hacking

## Gated Modal Types&#x20;

Depending on how the gated modal is configured, it will require different actions to _pass_ the gate and continue to the requested content. &#x20;

### `wfu-modal-gate` = ( _name_ )&#x20;

**Required.**  Indicates that this item is gated.&#x20;

Must be placed on one of these element types;&#x20;

| Element Type                                   | Behavior                                                                                           |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Link, Link Block, or Button element            | Gates the link. Once the gate is passed, the link is navigated.                                    |
| SA5 Modal, containing the `wfu-modal` element  | Gates the modal with a pre-modal.  Used when you are giving content, but want a gate before that.  |
| ~~Body element~~ 🧪                            | Gates the page. Covers the page with a "blur" and a modal state that                               |

{% hint style="info" %}
Future goals include e.g. partial page gating, like show a part of an article, prevent scrolling, and then undo that once the gate is opened.&#x20;
{% endhint %}

### `wfu-modal-gate-type` = ( _type_ )

Gate type is one of

* `view` ( default ) - The modal is seen, and closed. No special requirements.&#x20;
  * No attribute needed. The gate is considered passed when the modal is closed. &#x20;
* `button` - A specific button is clicked.&#x20;
  * `wfu-modal-gate-button` place this on the link or button that needs to be clicked. Modal will be closed and gate will be passed. &#x20;
* `submit` - Successful submission of a form
  * `wfu-modal-gate-submit` place this on the \<form> element. &#x20;

Future possibilities -&#x20;

* `func` - call a function to determine gate passage&#x20;

{% hint style="info" %}
Func could be used for e.g. calculate age from date of birth in a form, and confirm. &#x20;
{% endhint %}

<img src="../../.gitbook/assets/file.excalidraw (5).svg" alt="" class="gitbook-drawing">





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









wfu-







## Gate Types

* View the modal
* Click the button, e.g. **I Accept** &#x20;
* Successful form submit&#x20;



## Future&#x20;

Considering how this works with SA5 Trigger. &#x20;









