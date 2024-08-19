---
description: SA5 Tabs Future Plans
---

# Tabs Future Plans



## Roadmap&#x20;

| Feature                   | Now                                                           | Planned                                             | Considering                                                              |
| ------------------------- | ------------------------------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------ |
| Orientation               | Vertical or horizontal, defined by your Webflow tabs element  |                                                     |                                                                          |
| Animations for open/close |                                                               |                                                     | Considering some means to support WF Interactions, or else GSAP themes.  |
| Dynamic initialization    |                                                               | Select on # or query param, and scroll-to           |                                                                          |
| Modes                     |                                                               | Tab change on hover                                 | _Tabcordion_                                                             |
| Keyboard                  |                                                               | Possible keyword support, review a11y requirements  |                                                                          |

{% hint style="success" %}
The **Tabcordion** mode mentioned above is a conceptual hybridization of a tab element and an accordion.  It's intended to solve the issues surrounding tab elements on mobile devices.  How the implementation might best work is not yet determined.&#x20;
{% endhint %}

## JavaScript API

### Methods&#x20;

| Feature                     | Now                                                 | Planned | Considering |
| --------------------------- | --------------------------------------------------- | ------- | ----------- |
| Programmatic Navigation     | Navigate to tab number, first, last, next, and prev |         |             |
| Add / remove / reorder tabs |                                                     |         | Considering |

### Events

| Feature              | Now                      | Planned                                                                              | Considering |
| -------------------- | ------------------------ | ------------------------------------------------------------------------------------ | ----------- |
| Tab changed event    | Occurs on any tab change | Will reconsider how this should work in multi-item mode                              |             |
| Tab can change event |                          | Can open, can close, etc.  Give dev the ability to reject an open or close request.  |             |







Additional thoughts;&#x20;

* Detection of common hidden state scenarios, and numbering, selection etc. based on the visible indices only.&#x20;
  * Conditional visibility
* Auto-select N ( e.g. if first is conditionally hidden, we get tab 2 )&#x20;
* Addition of informational attributes on the tabs outer element
  * no tabs state, tab count&#x20;
* Console log error if more than one tab element is accidentally assigned the same unique name.&#x20;

Some things we're considering;&#x20;

{% hint style="danger" %}
These are under consideration for implementation, and not yet implemented.&#x20;
{% endhint %}

## Events <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### Pre-change event

Fire an event before a tab change happens, and allow the responding code to approve/deny the change. This is very interesting, for special flows such as multi-step forms.&#x20;

However it requires;

* Completely overriding the default webflow.js event handler
* Replacement of that default handler with an SA5 variant&#x20;
* An event origination flag, i.e. user-initiated v. code-initiated&#x20;

## Change on Hover <a href="#getting-started-nocode" id="getting-started-nocode"></a>

[https://discourse.webflow.com/t/open-tab-pane-on-hover-instead-of-click/218539/3](https://discourse.webflow.com/t/open-tab-pane-on-hover-instead-of-click/218539/3)

## Select on Query or #&#x20;

* `#hash` on query
  * Use tab name as default
  * Or explicit name ( e.g. CMS-based ) `wfu-tab`
    * Auto-gen these on CMS layout to tabs
      * Will need an `wfu-tab-ns` also&#x20;
* Scroll-to option
* URL change option as tab changes
* In-page link from `#hash` links or NS `#ns.ksdfj`&#x20;



[https://webflow.com/made-in-webflow/website/simple-tab-link](https://webflow.com/made-in-webflow/website/simple-tab-link)

Approaches-

Event listener on links

```
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (event) {
        event.preventDefault();
        const targetId = this.getAttribute('href').substring(1);
        const targetElement = document.getElementById(targetId);

        if (targetElement) {
            window.scrollTo({
                top: targetElement.offsetTop,
                behavior: 'smooth'
            });
            
            // Custom script when a hashtag link is clicked
            customFunction();
        }

        // Update the URL hash without causing a page jump
        history.pushState(null, null, `#${targetId}`);
    });
});

function customFunction() {
    console.log('Hashtag link clicked!');
}

```

Hashchange event;

```
window.addEventListener('hashchange', function() {
    console.log('Hash changed:', location.hash);

    // Custom script when the hash changes
    customFunction();
});

function customFunction() {
    console.log('Hashtag link clicked!');
}

```

Intercept Link Clicks with event delegation

```
document.addEventListener('click', function(event) {
    const target = event.target;

    if (target.tagName === 'A' && target.getAttribute('href').startsWith('#')) {
        event.preventDefault();
        const targetId = target.getAttribute('href').substring(1);
        const targetElement = document.getElementById(targetId);

        if (targetElement) {
            window.scrollTo({
                top: targetElement.offsetTop,
                behavior: 'smooth'
            });

            // Custom script when a hashtag link is clicked
            customFunction();
        }

        // Update the URL hash without causing a page jump
        history.pushState(null, null, `#${targetId}`);
    }
});

function customFunction() {
    console.log('Hashtag link clicked!');
}

```





