---
description: SA5 Slider Future plans
---

# Future

Pause on hover controls;

[https://discourse.webflow.com/t/controlling-slider-preventing-hover-pause-with-jquery/160730](https://discourse.webflow.com/t/controlling-slider-preventing-hover-pause-with-jquery/160730)

[https://discourse.webflow.com/t/disable-slider-pause-on-hover/133172/19](https://discourse.webflow.com/t/disable-slider-pause-on-hover/133172/19)

Controls;

* Pause / Play&#x20;

Slide manufacture;

* Add slides from static elements
* Load slides from CMS
* Allow insertion of slides at specific points in-between existing slides ( start, end middle )&#x20;
  * insert-index
* Randomize slides&#x20;
* GTM slide view and slide-interact events&#x20;

More robust error messaging;

* Notify user in error console log if the slider is broken&#x20;

Plan to add;&#x20;

* Detection of common hidden state scenarios, and numbering, selection etc. based on the visible indices only.&#x20;
  * Conditional visibility
* Auto-select N ( e.g. if first is conditionally hidden, we get tab 2 )&#x20;
* Addition of informational attributes on the tabs outer element
  * no tabs state, tab count&#x20;





## Per-Slide Advance Timing     &#x20;

```javascript
function slideNext() {
    console.log("Sliding to next"); // Replace with your actual slide advancing logic
}

const delays = [2000, 5000, 3000, 1000, 8000]; // Array of delay times in milliseconds

function executeSlideSequence(index = 0) {
    if (index >= delays.length) return; // Stop when all delays are used

    setTimeout(() => {
        slideNext();
        executeSlideSequence(index + 1); // Recursive call for the next delay
    }, delays[index]);
}

// Start the sequence
executeSlideSequence();
```











