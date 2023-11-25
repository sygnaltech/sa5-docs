---
description: Webflow Tools that Make Your Site Better
---

# Sygnal Attributes v5

{% hint style="success" %}
**SA5 is the lastest version of Sygnal's Webflow Utilities Library.**\
The tools here are 100% free, and 100% designed for Webflow. &#x20;
{% endhint %}

A lot of new features have already been released and many more are in the works. With that comes a _major rewrite_ of this documentation.&#x20;

We've begun including our dev team and roadmap notes in these docs so that they are available for community comment and discussion.&#x20;

## Navigating the Docs

* Documentation is organized by library&#x20;
* At the top of most libraries, you'll two important pages-
  * 🔍 **About this Library**, which gives you an overview of the capabilities
  * 🚀 **Quick Start**, which gives you the _library code_ you need&#x20;
* Within each library the features are grouped separately
* A _lot of features_ have **subpages**- make sure to click the **>** to expand those sections\
  ![](<.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png>)
* 🧪 indicates EXPERIMENTAL items, which are **not yet available**&#x20;
* 📝 indicates NOTES, which are primarily for the dev team&#x20;
* ▶️ indicates VIDEO TUTORIALS, which we're just beginning to add

## **What’s new in v5?**

**The tech changes we've made in v5 open the doors to a lot of new capabilities.**

{% hint style="success" %}
If you are using v4, none of these changes will affect your current websites. \
Since all of our CDN URLs are version-locked, you’ll continue to use the same libraries you are using now until you upgrade to the newer versions, _someday_, if you want to.
{% endhint %}

### The v5 Tech Stack

* We’ve changing from a JavaScript ES6 codebase to TypeScript
* We’ve changed fully from CSS to SASS.
* We’ve eliminating all use of jQuery in the libraries.
* We’ve separated classes through the library into discrete source files
* We’ve bundled the distributed files differently for even greater efficiency
* We've integrated debugging features&#x20;

We’re excited about the tremendous capabilities the new stack gives us.

### **Switching to v5**

If you _choose to_ switch to the upgraded v5 libraries at some point, you’ll see a few minor integration changes;

**Javascript** \<script> elements;

* Will be moved from the **before-/body** section to the **before-/head** section of your pages and site-wide code settings.
* The library URLs will change to point at the `/dist/` path, rather than the `/src/` path.
* You'll also notice that the `type=module` is dropped

**CSS** `<link>` elements will essentially remain unchanged, and will continue to point to `/dist/css/`

{% hint style="info" %}
All of this is covered in the docs for each feature, and we’ll update the docs as each library is migrated, so that you can upgrade them if you choose to.
{% endhint %}

#### What about attribute or code changes?

You can simply reference the new libraries _with no changes_ to your _custom attributes_ or existing features- and you’ll still get the enhanced features and performance benefits.

#### Will I need to upgrade to v5 eventually?

**Nope!** If you’re happy with things as they are and don’t need any of the new features, you don’t need to change a thing. v4 will continue to run indefinitely.&#x20;

