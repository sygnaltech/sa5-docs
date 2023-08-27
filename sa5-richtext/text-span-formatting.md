---
description: Add Highlighting, Code and other styles to your Rich Text Elements
---

# Text SPAN Formatting 🧪



Webflow's rich text element does not offer a span styling for text, which severly limits the options for custom text formatting. When you want to be able to highlight text or display a piece of code, you're forced to find other options.&#x20;

Currently one approach we use often is to repurpose the Superscript & Subscript styling that often are not needed in a typical blog.&#x20;

Currently this can be done in the designer, but we're considering SA5 features to expand on this;



## Under Consideration

Goals;

* Repurpose Webflow's \<sup> and \<sub> in rich text elements, for other purposes.&#x20;
* Make the in-designer experience WYSIWYG&#x20;

### OPTION 1&#x20;

CSS approach;

Normalize sub, still is a \<sub> element, but it no longer descends. Same approach for sup.&#x20;

```css
[wfu-richtext-...] sub {
    font-size: inherit;
    position: inherit;
}
```

Can target specific RTE's through attributes;

\[wfu-richtext-sub]

\[wfu-richtext-sup]





```css
color: #ff9cb5; 
background-color: #404047;
border-radius: 2px;
padding-left: 0.2rem;
padding-right: 0.2rem;
font-family: Roboto Mono, sans-serif;
font-size: 16px;
position: static;
```

### OPTION 2

Convert element to `<span>`. &#x20;



