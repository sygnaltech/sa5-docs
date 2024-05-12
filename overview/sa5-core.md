---
description: The central engine
---

# SA5 Core

For some time we've been developing the central engine shared by all libraries. It has a few key roles;

* Centralized debugging and debug state management&#x20;
* Event handler registration
* Configuration handler registration
* Global vars

Eventually, we'll be expanding it to add a few other key capabilities;

* Remote monitoring
* Smart-loading

### What is Smart Loading?

Smart Loading is a means to conveniently detect and load SA5's many libraries dynamically, depending on the configurations found in the webpage-

* Script config blocks
* SA5 custom attributes

Features;

* Drop in one references, and all libs are automatically accessible ( same version as core )
* Detection of unknown attributes, or misspelled attributes, or obsolete
*

## Loading Technique

Pre-DOM load

e.g. for inline script changes like SEO work

Post-DOM load

Most work is done here&#x20;

```
if (document.readyState !== 'loading') {
    console.log('document is already ready, just execute code here');
    myInitCode();
} else {
    document.addEventListener('DOMContentLoaded', function () {
        console.log('document was not ready, place code here');
        myInitCode();
    });
}

function myInitCode() {}
```
