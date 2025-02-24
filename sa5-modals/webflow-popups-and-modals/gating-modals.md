---
description: Restrict access to content with an SA5 gate
---

# Gating Modals 🧪

**SA5 Gating Modals** are the same as a regular modal, but they describe a special "gating trigger" configuration.  When the user&#x20;



<img src="../../.gitbook/assets/file.excalidraw (6).svg" alt="" class="gitbook-drawing">







wfu-trigger-ga



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

**Required.**  Indicates that a specific link or modal click trigger element is gated.&#x20;

Its behavior depends on the type of element it is placed on which must be one of;&#x20;

| Element Type                                   | Behavior                                                                                           |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| SA5 Modal, containing the `wfu-modal` element  | Gates the modal with a pre-modal.  Used when you are giving content, but want a gate before that.  |
| Link, Link Block, or Button element            | Gates the link. Once the gate is passed, the link is navigated.                                    |
| ~~Body element~~ 🧪                            | Gates the page. Covers the page with a "blur" and a modal state that.                              |

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



## Code Notes&#x20;

Gated link &#x20;

```
<script> 
document.addEventListener("DOMContentLoaded", () => { 

    const modalElements = document.querySelectorAll('[gated-link="configure"]');
    modalElements.forEach(element => {
        element.addEventListener("click", () => {
						event.preventDefault(); 

            // Check if form was already submitted
            const formSubmitted = localStorage.getItem("formSubmitted");
            if (formSubmitted) {
            
            		navigateToLink(element); 
            		// redirect to link
//                 window.location.href = element.href;
                
            } else {
                console.log("Form not submitted yet. Showing modalForm...");
                sa5.controllers.modals.display("modalForm", true); 
                
                // Store the clicked link for later use
                localStorage.setItem("pendingRedirect", JSON.stringify({ href: element.href, target: element.target }));                
            } 
            
        });
    });
    
    const form = document.getElementById("email-form");
    form.addEventListener("submit", function (event) {
        
				// Set formSubmitted flag
        localStorage.setItem("formSubmitted", "true"); 
        
        sa5.controllers.modals.closeAll(); 
        
				// redirect to link
        // Retrieve and navigate to the stored pending redirect link
        const pendingRedirect = localStorage.getItem("pendingRedirect");
        if (pendingRedirect) {
            const { href, target } = JSON.parse(pendingRedirect);
            localStorage.removeItem("pendingRedirect"); // Clean up

            const tempLink = document.createElement("a");
            tempLink.href = href;
            tempLink.target = target;
            navigateToLink(tempLink);
        }
        
    });    
    
}); 

/**
 * Handles link navigation while respecting the target attribute.
 * @param {HTMLAnchorElement} linkElement - The link element to navigate to.
 */
function navigateToLink(linkElement) {
    if (linkElement.target && linkElement.target !== "_self") {
        window.open(linkElement.href, linkElement.target);
    } else {
        window.location.href = linkElement.href;
    }
}
</script>
```



### Gated Modal

```
<script> 
document.addEventListener("DOMContentLoaded", () => { 

    const modalElements = document.querySelectorAll('[gated-modal="modalForm"]');
    modalElements.forEach(element => {
        element.addEventListener("click", () => {

            // Check if form was already submitted
            const formSubmitted = localStorage.getItem("formSubmitted");
            if (formSubmitted) {
                console.log("Form already submitted. Showing modal1...");
                sa5.controllers.modals.display("modal1", true); 
            } else {
                console.log("Form not submitted yet. Showing modalForm...");
                sa5.controllers.modals.display("modalForm", true); 
            } 
            
        });
    });
    
    const form = document.getElementById("email-form");
    form.addEventListener("submit", function (event) {
        
				// Set formSubmitted flag
        localStorage.setItem("formSubmitted", "true"); 
        
        sa5.controllers.modals.closeAll(); 
        sa5.controllers.modals.display("modal1", true); 

    });    
    
}); 
</script>


```











