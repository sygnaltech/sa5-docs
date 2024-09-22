---
description: Preserve line breaks in multiline text
---

# Preserve Line Breaks

{% hint style="danger" %}
**NOT RELEASED**\
Webflow's form notifications do not respond to any form of textarea line break modification, including `\r\n`, `\n`, `<br>`, `\n\n`, etc.  This makes this feature somewhat useless with Webflow's form notifications. &#x20;

If you need line breaks in your rich text areas, we recommend Basin instead.&#x20;
{% endhint %}

## Required Attributes

### Add `wfu-form`&#x20;

Add `wfu-form` to the **form** or **form block** element directly.&#x20;

### Add `wfu-form-textarea`&#x20;

Designate the checkboxes you want removed-if-unchecked with the following attribute and value-

`wfu-form-textarea` = `preserve-linebreaks`&#x20;





* Apply this to the element with `wfu-form` on it, if you want all checkboxes to be affected
* Apply this to an **individual checkbox** element if you want only specific checkboxes to be affected





```
<script>
document.addEventListener("DOMContentLoaded", function() {
    var form = document.getElementById('id-of-form');
    form.addEventListener('submit', function(event) {
        event.preventDefault(); // Prevent the form from submitting immediately

        // Get the textarea value
        var textarea = document.getElementById('id-of-textarea');
        var modifiedText = textarea.value.replace(/(\r\n|\r|\n)/g, '\\n');

        // Set the modified text back to the textarea or prepare it for sending
        textarea.value = modifiedText;

        // Now submit the form programmatically
        form.submit();
    });
});
</script>
```
