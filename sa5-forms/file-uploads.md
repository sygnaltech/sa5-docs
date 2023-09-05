# File Uploads 📝

[https://usebasin.com/docs/features/file-uploads](https://usebasin.com/docs/features/file-uploads)

{% code overflow="wrap" %}
```html
// Some code
<form accept-charset="UTF-8" action="https://usebasin.com/f/1a2b3c4d5e6f" enctype="multipart/form-data" method="POST">
...
<input type="file" name="resume" ></input>
...
</form>
```
{% endcode %}

Concept...&#x20;

* Form-
  * Configure for basin
  * Place e.g. the basin URL in action&#x20;
* Drop a standard input field
  * Tag it \[wfu-form-field-file]=
  * Name becomes the name of the file
  * \[wfu-form-field-multiple]
* Place e.g. the basin URL in action&#x20;

Internally we;

* Form-
  * Add enctype="multipart/form-data" to the form
  * Ensure it is POST
  * Verify Basin URL is a legit basin URL, warn otherwise&#x20;
* Field
  * Type = file
  * multiple option and \[]&#x20;

{% code overflow="wrap" %}
```html
// Some code
<form accept-charset="UTF-8" action="https://usebasin.com/f/1a2b3c4d5e6f" enctype="multipart/form-data" method="POST">
...
<input type="file" name="attachments[]" multiple></input>
...
</form>
```
{% endcode %}

Ideally we want to make this handler-agnostic, so we add a form-setup feature to handlers, and a form-validate feature&#x20;



[https://discourse.webflow.com/t/form-submissions-to-third-party-service-with-native-interactions/63401/28](https://discourse.webflow.com/t/form-submissions-to-third-party-service-with-native-interactions/63401/28)

You must include a parameter enctype=“multipart/form-data” in your form element, otherwise it will not submit the file as a file but only the filename.

[https://discourse.webflow.com/t/how-to-add-file-upload-input-to-a-webflow-form-with-basin-endpoint/100977/9](https://discourse.webflow.com/t/how-to-add-file-upload-input-to-a-webflow-form-with-basin-endpoint/100977/9)
