---
description: Inject custom code from the CMS anywhere in your Webflow page.
---

# CMS Code Injection ❺🧪

## Goals&#x20;

* Store custom code in the CMS so that it can be individually part of a demo, blog post, etc.&#x20;
* Make the code accessible and manageable using a plain text multiline field ( rather than the HTML embed hack )&#x20;
* Allow positioning of the code in the `<head>`, or in the `<body>` as desired&#x20;
* Handle decoding automatically&#x20;
* Support multiple, compound, complex arrangements, e.g. multiple `<script>`'s, JSON-LD, `<style>` chunks and so on. &#x20;
  * Basically an insertable chunk of HTML.&#x20;

## Prototype

{% hint style="danger" %}
This is highly dangerous in that it injects raw script into the page. Make certain you are 100% in control of the fields you are injecting and that they contain no user-generated content ( UGC ). &#x20;
{% endhint %}

* Add your plaintext multiline field to your CMS collection.&#x20;
* Add your code there including `<script>` or `<style>` element wrappers.&#x20;
* Position the script below where you want it, in the `<head>` or `<body>` custom code area of your page, or in an HTML embed.  &#x20;
* Replace the encoded content value between the backticks with your + Add field to insert your custom script.&#x20;

```html
<script>
    // Step 1: Define your HTML-encoded content
    const encodedContent = ` ADD YOUR CODE EMBED FIELD HERE `;

    // Step 2: Decode the HTML-encoded content
    function htmlDecode(input) {
        const doc = new DOMParser().parseFromString(input, "text/html");
        return doc.documentElement.textContent;
    }
    const decodedContent = htmlDecode(encodedContent);

    // Step 3: Create a temporary container
    const tempContainer = document.createElement('div');
    tempContainer.innerHTML = decodedContent;

    const currentScript = document.currentScript;
  
    // Step 4: Append the contents to the desired location
    // For example, appending to the document body
    while (tempContainer.firstChild) {
//        document.body.appendChild(tempContainer.firstChild);
        currentScript.parentNode.insertBefore(tempContainer.firstChild, currentScript);
    } 

    // Step 5: Remove this injector script element
    currentScript.parentNode.removeChild(currentScript);

</script>
```



*
  * &#x20;
