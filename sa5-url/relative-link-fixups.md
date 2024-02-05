---
description: Fix CMS and in-page links to their correct relative form
---

# Relative Link Fixups ❺⛔



{% hint style="success" %}
**NO LONGER NEEDED!**

10-Dec-2023 - Webflow has fixed the CMS link field so that it will now accept _relative paths_. And there was much rejoicing.&#x20;

* Root-relative URLs like `/about/us` are fully supported
* Page-relative URLs like `../about` are not supported, but who would use these today anyway?&#x20;
* Localization of these URLs is not directly supported \[ yet? ].  Let's say your you have an English ( primary-locale ) site with a German alt-locale. If you store a link to `/about` in the CMS, and a user is viewing the German translated version of your CMS page, clicking that link will take them to `/about` rather than e.g. `/de/about`. This means they'll be switched back to the English locale.&#x20;
{% endhint %}

{% embed url="https://twitter.com/memetican/status/1733603236685422608" %}

The two things that have fundamentally defined the web since the beginning are HTML, and URLs. Since the beginning, links have been at the center of the Internet universe.&#x20;

They even gave the World Wide Web its name.&#x20;

But there are many different kinds of links;&#x20;

1. <mark style="color:green;">**Absolute URLs**</mark>: These URLs provide the full path to the resource, including the protocol (http, https), domain name, directory path, and file or resource name. For example, `https://www.example.com/images/pic.jpg`.
2. <mark style="color:green;">**Root-relative URLs**</mark>: These are a type of relative URL that start from the root of the website. They start with a slash (`/`). For example, `/images/pic.jpg` would resolve to `https://www.example.com/images/pic.jpg` if you're anywhere on `www.example.com`.
3. <mark style="color:orange;">**Protocol-relative URLs**</mark><mark style="color:orange;">:</mark> These URLs start with `//` and use the same protocol (http or https) as the current page. For example, `//www.example.com/images/pic.jpg` would use http or https depending on the protocol of the page it's used on.
4. <mark style="color:red;">**Relative URLs**</mark>: These URLs provide the path to the resource relative to the current location. They don't include the protocol or domain name. For example, if you're on `https://www.example.com/pages/`, a relative URL might look like `../images/pic.jpg`, which would resolve to `https://www.example.com/images/pic.jpg`.

Webflow supports the first two solidly. The third is quite specialized and is typically used for script references.&#x20;

But relative URLs are effectively unsupported.&#x20;

You have the ability to link to a page on the same site, or to an external URL, but not to a relative URL.&#x20;

## Use cases

For designers and developers using Webflow, there are a few places this causes problems;

* In the CMS, when you want to link to something on the site, using the Link field type
* In a page, when you want to link to any page on the site, while including a querystring&#x20;
* In a page, when you want to link to any page on the site, while including a querystring&#x20;
* Special pathing, when you are using a reverse proxy.&#x20;

## How Webflow Breaks Relative Links <a href="#usage-notes" id="usage-notes"></a>

In an HTML link, all of these are valid relative links:

1. `./foo`: This link refers to a resource named "foo" in the same directory as the current page.
2. `foo`: This link also refers to a resource named "foo" in the same directory as the current page. It's equivalent to `./foo`.
3. `.?foo=bar`: This link refers to the current page (the `.` represents the current page), with a query string `foo=bar` added to the URL. However, this is not a common usage and might be confusing. It's more common to see just `?foo=bar`.
4. `?foo=bar`: This link also refers to the current page, with a query string `foo=bar` added to the URL. The browser will load the current page, but with `foo=bar` in the query string.

In the Webflow designer and editor, if you try to enter any of these as a link in a page, you must use the External Link type.&#x20;

When your page publishes, these links will become invalid, prefixed with `http://`, for example `http://./foo`, which the browser cannot access.

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

## Demonstration <a href="#usage-notes" id="usage-notes"></a>

The demo links in this page, shown as starting with a ? querystring, are relative links that this library fixes up.&#x20;

{% embed url="https://url-tracking.webflow.io/relative-links" %}
Demonstration page
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/url-tracking" %}
Cloneable site
{% endembed %}

## Usage Notes  <a href="#usage-notes" id="usage-notes"></a>

### In Webflow Link Elements

We identify and support these formats;

* Any link beginning with a `.`, meaning current page
* Any link beginning with a querystring demarcation `?`. &#x20;

### In CMS Link Fields

**Webflow’s CMS feature has a significant limitation in that the CMS knows nothing about its containing site.**

As a result of this design gap, it’s currently not possible to link from a CMS collection item to a known page in your site, in the same way you can link within the designer.

CMS’s have a Link field type, however a second limitation prevents the use of relative paths, which means you cannot even link to e.g. `/about/`.

How to use;

* In any CMS where you want a relative link to a site page, simply place that link in a CMS link field, with `http://self/` or `https://self/` as the protocol and hostname.
  * e.g. to link to `/about`, you’d write it as `https://self/about`.

The link fixup library will find and correct this link to a proper relative link of `/about`.

{% hint style="success" %}
As of SA5 v5.2.15 support has been added for CMS-based relative links that include querystrings or hashtags.&#x20;
{% endhint %}



## Getting Started ( LOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Add your Configuration Callback

Add this configuration section above right after the library in your **before HEAD** custom code. Typically this will be in the site-wide custom code configuration.&#x20;

\
