---
description: What's new, and what's changing.
---

# Sygnal Attributes v5

**In July-2023, we've started work on Sygnal Attributes v5 ( SA5 )!** &#x20;

You’ll begin seeing some small feature additions initially, and minor feature and interface improvements as we migrate code from v4.

{% hint style="success" %}
None of this work will affect your current websites. Since all CDN urls are version-locked, you’ll continue to use the same libraries you are using now.
{% endhint %}

## **What’s new in v5?**

**The tech changes we're making in v5 open the doors to a lot of new capabilities.**

Initially, you'll notice these;

* Faster load times
* More robust features
* Integrated debugging
* No more jQuery dependencies

## The v5 Tech Stack

* We’re changing from a JavaScript ES6 codebase to TypeScript
* We’re changing fully from CSS to SASS.
* We’re eliminating all use of jQuery in the libraries.
* We’re separating classes through the library into discrete source files
* We’re bundling the distributed files differently for even greater efficiency

We’re excited about the tremendous capabilities the new stack gives us.

## The v4 to v5 Migration Plan

Because we're migrating the libraries gradually, our plan is to run v4 and v5 libraries side-by-side in the same time. You'll be able to use either, or both, depending on the features you want.

_Documentation will contain install instructions for each, for the feature you're using._&#x20;

## **Switching to v5**

If you _choose to_ switch to the upgraded v5 libraries at some point, you’ll see a few minor integration changes;

**Javascript** \<script> elements;

* Will be moved from the **before-/body** section to the **before-/head** section of your pages and site-wide code settings.
* The library URLs will change to point at the `/dist/` path, rather than the `/src/` path.
* You'll also notice that the `type=module` is dropped

**CSS** `<link>` elements will essentially remain unchanged, and will continue to point to `/dist/css/`

{% hint style="info" %}
All of this is covered in the docs for each feature, and we’ll update the docs as each library is migrated, so that you can upgrade them if you choose to.
{% endhint %}

### What about attribute or code changes?

When v5 is completed, you should be able to simply reference the new libraries _with no changes_ to your _custom attributes_ or existing features- and you’ll still get the extended feature set and performance benefits.

If any breaking changes are introduced in v5, we'll specify the feature that is affected and what is different in its capabilities or configuration. You'll know before you upgrade that features.

### Will I need to upgrade to v5 eventually?

**Nope!** If you’re happy with things as they are and don’t need any of the new features, you don’t need to change a thing.&#x20;

_**Even when v5 is fully released, v4 will continue to run indefinitely.**_&#x20;

