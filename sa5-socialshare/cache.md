---
description: Convert a link element into an email sharing tool for current page.
---

# Email Social Share ❺

Designed to make a link element work as a sharing mechanism for the current page.

When clicked, it invokes the user's defined email program to send a message, and populates the subject and body, including the link to the current page.

The user then enters to To, and sends it.&#x20;

## Demonstration

{% embed url="https://webflow.com/made-in-webflow/website/sa5-social-share" %}

## Getting Started  <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

### STEP 1 - Add the Library  <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply `wfu-socialshare` to Desired Elements <a href="#step-2---apply-wfu-query-param-to-desired-elements" id="step-2---apply-wfu-query-param-to-desired-elements"></a>

See Usage Notes for details.&#x20;

## Usage Notes

### `wfu-socialshare` = `email`

**Required.**  Place directly on the link that you want to use for social sharing.&#x20;

{% hint style="warning" %}
This will replace any existing `src` on the link with the `mailto:` URL SA5 forms for you.&#x20;
{% endhint %}

### `wfu-socialshare-subject` = ( subject text you want on the email )

**Optional.** Place on the element with `wfu-socialshare`. &#x20;

### `wfu-socialshare-message` = message you want to preface the link

**Optional.** Place on the element with `wfu-socialshare`. &#x20;

Note the message can contain line-breaks, by using the `\n` character sequence.&#x20;

### UTM Tracking

If you want to add tracking information to the link, you can use SA5's UTM Tracking attributes here as well, on this same email element.&#x20;

[utm-tracking.md](../sa5-analytics/utm-tracking.md "mention")

In general, we'd recommend something like;&#x20;

<table><thead><tr><th width="272">SA5 attribute</th><th>Example Value</th><th>Notes</th></tr></thead><tbody><tr><td><code>wfu-link-utm-source</code></td><td><code>email</code></td><td></td></tr><tr><td><code>wfu-link-utm-medium</code></td><td><code>share</code></td><td>Indicates that it was shared</td></tr><tr><td><code>wfu-link-utm-campaign</code></td><td><code>blog</code></td><td>Or similar ( news, recipe... )</td></tr><tr><td><code>wfu-link-utm-content</code></td><td>Your Article Title</td><td>CMS-bind this one if you're in a collection list or collection page. </td></tr></tbody></table>



