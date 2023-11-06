---
description: Uploads are Easy with Basin
---

# File Uploads

Basin also supports File Uploads. This is easily added to your Webflow forms by placing an HTML Embed with a file input element, e.g.;

```html
<input type="file"
       name="avatar"> 
```

## Restricting File Types

If you just want a specific type of image, the accept param can be added to restrict file types.&#x20;

```html
<input type="file"
       name="avatar"
       accept=".webp, .png, image/jpeg">
```

You specify the [unique file-type specifiers](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file#unique\_file\_type\_specifiers) of the files you want to allow, and browsers will generally do a good job of restricting the file types that can be uploaded based on that. &#x20;

![](<../../../.gitbook/assets/image (2).png>)

Generally you can specify;&#x20;

* Valid case-insensitive file extensions such as `.pdf`
* Valid MIME type strings, e.g. `image/jpeg`
* File-type category specifiers-&#x20;
  * `audio/*` means any audio file
  * `video/*` means any audio file
  * `image/*` means any audio file

## Multiple files

Simply add `multiple`, and brackets `[]` after the name.&#x20;

```html
<input type="file"
       name="avatar[]"
       accept="image/webp, image/png, image/jpeg"
       multiple>
```

[https://usebasin.com/docs/features/file-uploads](https://usebasin.com/docs/features/file-uploads)

## Notes&#x20;

[https://usebasin-recaptcha.webflow.io/ajaxified](https://usebasin-recaptcha.webflow.io/ajaxified)

[https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file)

[https://discourse.webflow.com/t/how-to-add-file-upload-input-to-a-webflow-form-with-basin-endpoint/100977/8](https://discourse.webflow.com/t/how-to-add-file-upload-input-to-a-webflow-form-with-basin-endpoint/100977/8)

[https://discourse.webflow.com/t/form-submissions-to-third-party-service-with-native-interactions/63401/49?page=2](https://discourse.webflow.com/t/form-submissions-to-third-party-service-with-native-interactions/63401/49?page=2)

Hack add enctype=multipart/mime to FORM; does not appear to be needed ( with AJAX forms enabled ).&#x20;

{% code overflow="wrap" %}
```html
<script>
    // Get the closest form element relative to the script tag
    const scriptTag = document.currentScript;
    const formContainer = scriptTag.closest('form');
    if (formContainer) {
        formContainer.setAttribute('enctype', 'multipart/form-data');
    }
</script>
```
{% endcode %}

