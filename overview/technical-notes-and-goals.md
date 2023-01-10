# Technical Notes & Goals

## Design Philosophy

#### Separation of Functionality <a href="#separation-of-functionality" id="separation-of-functionality"></a>

As the library grows, I found the need to partition the code better for accessibility & reusability.

* Webflow-specific code is being distinguished from more general functionality.
* Libraries specific to Webflow implementation are prefixed with `webflow-`.
* Other libraries will be named, grouped and prefixed according to the functional intent and the platforms they pertain to.
* This means that much of the functionality here can be used in non-Webflow sites, or in sites that you are hosting separately. Around that capability is a Webflow-specific wrapper that applies those features in Webflow’s unique HTML-generation and hosting-environment context.

#### 3 Distinct Integration Approaches <a href="#3-distinct-integration-approaches" id="3-distinct-integration-approaches"></a>

I want to embrace the reality that many Webflow designers are unfamiliar with programming, while others need maximum functionality.

To support a wide range of users, I’m conceptually dividing integration approaches into 3 zones;

* **Code.** _Programmers_ will generally use the libraries under `src/modules` directly. These functions and libraries can be arranged to accomplish complex tasks with unique configurations, and using these modules directly gives you full access to their capabilities.
* **Lo-Code.** _Designers_ with basic scripting knowledge are provided with _locode_ libraries that encapsulate the most commonly-used functionality into single function calls. These libraries exist under `/src/locode` and have a `-helper` suffix. These will provide the core functionality of the full libraries, with minimal setup.
* **No-Code.** Where possible, I intend to offer codeless possibilities where the functionality is automatically added by simply adding the library. Paste in the library refernce, tag your elements for the functionality you want, and everything else happens automatically. This entirely avoids script-writing, while giving you much of the functionality designers want.

## **Technical Notes**

**Webflow Utilities (WFU)** is an experimental project as much as a practical toolset. Where possible, I’m employing the latest javascript technologies as a practical implementation exercise, and to test their capabilities.

### Webflow-centric Design <a href="#webflow-centric-design" id="webflow-centric-design"></a>

All of the tools in this library are designed specifically to work with websites that are built and hosted on Webflow.

This means;

* I prioritize HTML5 generation, with little attention to backwards compatability.
* I use jQuery, which is present in all Webflow hosted sites.
* Script files are be hosted externally to the site. In-site scripting is limited to “glue” and configuration scripts.
* I’m prioritizing solutions which overcome limitations & problems in Webflow, even if they wouldn’t be a common issue on other platforms.

### Redesigned Using ES6 Modules <a href="#redesigned-using-es6-modules" id="redesigned-using-es6-modules"></a>

As of 3.0, WFU uses [JavaScript modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) as a way to better define and separate code. These are widely supported across modern browsers, however are not supported by Internet Explorer.

Without the ability to use NPM, javascript modules appear to be the most effective way to separate and re-use use code between the libraries.

_Note, I’m using the `.js` extension on our modules rather than `.ejs`, as this currently appears to be the recommended practice. However, these are ES6 modules, so you will need to specify that in your script references._

If you’re unfamiliar with ES6 modules, accessing them looks like this;

Let’s suppose you want to call `myFunc()` from your Webflow page. In the “Before /BODY” code area, you might include this;

```
<script type="module">
    import { myFunc } from 'some-wfu-library.js';
    $(function () {
        myFunc();
    }
</script>
```

Notes;

* The `type="module"` on the `<script>` element is important, to allow ES6 use in your script.
* Modules are included through `import`, where you specify the function(s) you want to access, and the path to the `.js` library.
* You can use other javascript and jQuery 100% as normal.

I’ll give specific examples of script you can use with each library.

### Object-Oriented patterns <a href="#object-oriented-patterns" id="object-oriented-patterns"></a>

For complex utility modules, our library is designed using OO patterns as much as possible.

## Future Plans

### Node Package Manager (NPM) <a href="#node-package-manager-npm" id="node-package-manager-npm"></a>

Ideally, I’d like to evolve this toolset as a proper NPM package, as it would allow for much richer scripting options, a plug-in style architecture, version and dependency management.

At the moment this is on the backburner, as I’m unfamiliar with using NPM to generate browser-compatible ES6 bundles.

_Contributors welcome._



\
