# Custom Form Submit Button

**Webflow's form submit button is a "closed" element that doesn't easily allow for customization such as adding an icon.**

To work around this, you can create your own "button" from a DIV containing whatever icons and text you like, and then use script and a click handler to submit your form.

{% hint style="info" %}
We'll add this formally to the SA5 lib but for now, here's an approach.&#x20;
{% endhint %}

Here's a simple implementation;

## Setup Notes

1. Create your custom button however you like
2. Add the `wfu-form-submit` attribute to the outer button
3. Add this script to the before-/body section of the page(s) which have your forms;&#x20;

```html
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      document.querySelectorAll('[wfu-form-submit]').forEach(function(button) {
        button.addEventListener('click', function() {
          const form = button.closest('form');
          if (form) {
            // Attempt to submit the form, triggering built-in validation
            if (form.checkValidity()) {
              form.submit();
            } else {
              // If form is invalid, trigger HTML5 form validation UI
              form.reportValidity();
            }
          } else {
            console.error('No form found to submit.');
          }
        });
      });
    });
  </script>
```

