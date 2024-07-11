---
description: Encode your email addresses to minimize spam on exposed email addresses.
---

# Encoded Email

Sometimes you want to put an email in your web pages and website footer, but exposing it directly to bots is just horriffic.&#x20;

## Usage Notes

Pick any link element which you want to display an email address in.

* Set it to a link of type email
* Take the email you want to use, and encode it using the tool below
* Paste the encoded email in as the email you want message sent to
* If you want to visually display the email as the link text, paste the encoded email as the link text as well
* Add the custom attribute of `wfu-email-encoded` to the link element&#x20;

That's it. The published page will contain an unrecognizable email address in it.  SA5 will then decode and display it once the library runs.&#x20;

You can use other standard features as well like email subject.&#x20;

## Encoding Tool

Use this Codepen to do the encoding; it will return a garbled-looking email but that is the same length as your original email ( for formatting purposes ).&#x20;

{% embed url="https://codepen.io/memetican/pen/WNqbaXp/34ff9018620476b83f8b1869e2989134" %}



