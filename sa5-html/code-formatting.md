---
description: Manage code formatting in your Webflow hosted page.
---

# Code Formatting ❺🧪

Webflow has added&#x20;

## Webflow's Feature

Auto-detect

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

### Auto-Detection and Auto-Formatting

Webflow appears to auto-detect the syntax of the language, and styles it according to a language-specific stylesheet.

Example, `https:` was identified as a `makefile` -

```
<code class="hljs language-makefile"><span class="hljs-section">https:</span></code>
```

Example, `olddomain.com` was identified as `undefined` -&#x20;

```
<code class="hljs language-undefined">olddomain.com</code>
```

At this point we do not know;

* Whether we can specify the language manually
* Whether we can control styling&#x20;
* Themes, etc.
* Whether the styling is aware of e.g. background color, for contrast&#x20;



<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>
