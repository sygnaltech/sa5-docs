---
description: Make your inline floating rich text images more responsive
---

# Responsive Inline Images

## Goals

* Support more responsive inline floating images e.g.
  * float right, 30% max width on desktop
  * float right, 50% max width on mobile landscape&#x20;
  * no float, 100% width on mobile portrait&#x20;

The goal is to make floating image respond well for mobile devices.&#x20;

## Sample Partial Implementation

Here's a sample;&#x20;

```html
<style>
@media screen and (max-width: 767px) {
  .w-richtext figure.w-richtext-align-floatright {
    max-width: 50% !important; 
  }
}
@media screen and (max-width: 479px) {
  .w-richtext figure.w-richtext-align-floatright {
    float: none !important; /* Remove the float */
    margin-left: 0 !important; /* Reset the left margin */
    clear: none !important; /* Reset any clearing */
    width: 100%; 
    max-width: none !important; 
  }
}
</style>
```





