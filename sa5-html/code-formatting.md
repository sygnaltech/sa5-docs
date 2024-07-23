---
description: Manage code formatting in your Webflow hosted page.
---

# Code Formatting ❺🧪

In early 2024, Webflow added the ability to style specific text as code.&#x20;

With in a rich text block - static, or CMS - you can select specific text, and format it as code ( on the same toolbar that you format bold and italics ), and Webflow will style it. This works in the designer and the editor as well, and with static or CMS-bound content. &#x20;

Here's a screenshot containing 5 examples;

* http:
* https:
* olddomain.com
* newdomain.com
* www.newdomain.com

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

### Auto-Detection and Auto-Formatting

Webflow attempts to auto-detect the syntax of the language, and styles it according to a language-specific stylesheet.

Example, `https:` was identified as a `makefile` -

```
<code class="hljs language-makefile"><span class="hljs-section">https:</span></code>
```

Example, `olddomain.com` was identified as `undefined` -&#x20;

```
<code class="hljs language-undefined">olddomain.com</code>
```

### Custom Formatting

> Currently, Webflow provides limited styling control over these code items, in that you can style undefined items only.&#x20;

You can style code items as a sub-element of your classed rich text block;

<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

However, this styling will ONLY apply to code elements that Webflow identifies as `undefined`. Code which is recognized as another type will have Webflow's own default formatting applied instead.&#x20;

Here's that same example with custom styling applied;&#x20;

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>Here, the blue items were recognized as <strong>makefile</strong> syntax, while the pink items were <strong>undefined</strong> and had my own custom styling applied correctly.</p></figcaption></figure>

### To Research

At this point we do not know;

* Whether we can specify the language manually
* Whether we can control styling in greater detail, e.g. for makefiles, js, and so on&#x20;
* Themes, etc.
* Whether the styling is aware of e.g. background color, for contrast&#x20;
* Differences between static and CMS-bound control &#x20;

## SA5 Opportunity

Yes;&#x20;

* Overriding all to "undefined" so they match document style.

Maybe;

* Option to theme, by syntax&#x20;
* Possibility of controlling the language applied to a specific code element



&#x20;

