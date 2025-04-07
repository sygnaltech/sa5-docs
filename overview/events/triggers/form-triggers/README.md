# Form Triggers 🧪



## Checkbox Trigger&#x20;



sa-trigger-form-checkbox-on = ( event name )&#x20;

sa-trigger-form-checkbox-off = ( event name ) &#x20;

## Button Trigger&#x20;



sa-trigger-form-button-click = ( event name )&#x20;



## Show / Hide Fieldset&#x20;

Usage notes;&#x20;

Must be a custom element `<fieldset>` wrapping the elements&#x20;

sa-action-form-fieldset-show = ( event name )&#x20;

sa-action-form-fieldset-hide = ( event name )&#x20;

sa-action-form-fieldset-toggle = ( event name )&#x20;

Use cases;

* Show / hide a group of inputs&#x20;
* Enable / disable validation automatically&#x20;

Technical notes;&#x20;

* Uses disabled on the fieldset directly, to novalidate all of the fields within so that the form can be submitted with the fields hidden &#x20;













