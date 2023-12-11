# CSS Isolation

Concept

See if it's possible to use client-side JS to proxy the styling of Webflow's RTEs ( RTB sub-elements ), so that they are CSS-isolated.

Problem;

* Webflow broadly selects RTBs in the CSS as e.g. `.my-richtext p`
* This means that any `p` element embedded by script or Embed in the RTB will be affected by that stying
* This breaks the ability to embed components, forms, CTAs, call-outs, etc easily&#x20;
  * Especially as none of this can be seen in the designer

Possible Solution;

* Generate new classes based on the existing styling, affix e.g. `_mutated` to the class
* Write this to a Style block&#x20;
* Assign the mutated class name to all of the desired RTE's in the RTB
  * &#x20;? Avoid Embeds

Mutated CSS gen concept;&#x20;

```javascript
function copyStyles(sourceClass, targetClass) {
    // Find an element with the source class
    var sourceElement = document.querySelector('.' + sourceClass);

    if (!sourceElement) {
        console.warn('No element found with class:', sourceClass);
        return;
    }

    // Get computed styles of the source element
    var styles = window.getComputedStyle(sourceElement);

    // Create CSS string from computed styles
    var cssText = Array.from(styles).map(key => `${key}:${styles.getPropertyValue(key)}`).join(';');

    // Create a style tag and append to head
    var styleTag = document.createElement('style');
    document.head.appendChild(styleTag);

    // Add the new class with copied styles
    styleTag.sheet.insertRule(`.${targetClass} { ${cssText} }`, 0);
}

// Usage
copyStyles('foo', 'bar');
```

Dislikes;&#x20;

* Will pick up everything in the computed style, including inherited styles. If those are changed e.g. css vars...&#x20;
