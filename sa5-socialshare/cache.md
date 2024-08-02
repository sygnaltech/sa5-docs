---
description: Convert a link element into an email sharing tool for current page.
---

# Email Social Share ❺

{% hint style="warning" %}
BETA. Attributes & features may change in the final release.&#x20;
{% endhint %}



## Social Share - Email

Designed to make a link element work as a sharing mechanism for the current page.

When clicked, it invokes the user's defined email program to send a message, and populates the subject and body, including the link to the current page.

The user then enters to To, and sends it.&#x20;

`wfu-socialshare` = `email`

`wfu-socialshare-subject` = subject you want on the email

`wfu-socialshare-message` = message you want to preface the link

Note the message can contain line-breaks, by using the `\n` character sequence.&#x20;

## UTM Tracking

If you want to add tracking information to the link, you can use SA5's UTM Tracking attributes here as well, on this same email element.&#x20;

[utm-tracking.md](../sa5-analytics/utm-tracking.md "mention")

In general, we'd recommend something like;&#x20;

<table><thead><tr><th width="272">SA5 attribute</th><th>Value</th><th>Notes</th></tr></thead><tbody><tr><td><code>wfu_link_utm_source</code></td><td><code>email</code></td><td></td></tr><tr><td><code>wfu_link_utm_medium</code></td><td><code>share</code></td><td>Indicates that it was shared</td></tr><tr><td><code>wfu_link_utm_campaign</code></td><td><code>blog</code></td><td>Or similar ( news, recipe... )</td></tr><tr><td><code>wfu_link_utm_content</code></td><td>Your Article Title</td><td>CMS-bind this one if you're in a collection list or collection page. </td></tr></tbody></table>



