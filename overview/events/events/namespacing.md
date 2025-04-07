---
description: Namespace your events for advanced CMS-driven use cases.
---

# Namespacing

One of the common scenarios in which SA5 events are used are to support CMS-driven modals and pop-ups.&#x20;

Example use cases;

* You have a CMS-driven directory of employees. Clicking any employee's photos should display a pop-up containing that employee's info, also from the CMS.&#x20;
* You have a map, with map pins, populated from the CMS.  Clicking a map pin should pop up information about the location, also from the CMS.&#x20;

## How Namespacing Works&#x20;

In these situations, we need each individual trigger ( button ) and action ( modal display ) to be directly connected, but we also need them to be separated from other events.&#x20;

Namespacing segregates these safely.&#x20;

## Usage Notes  &#x20;

The general usage pattern is;&#x20;

* Setup your triggers and actions as you usually would.&#x20;
* For the event name, data-bind the attribute value to the CMS item slug&#x20;

e.g. `sa-trigger-click` = ( _CMS item slug_ )&#x20;

* Add a unique namespace to both the trigger and the action&#x20;

e.g. `sa-trigger-click:ns` = `employee` &#x20;

## Usage Notes Patterns &#x20;

### `sa-trigger-*:ns` = ( _namespace_ )&#x20;

All triggers support the `:ns` namespace suffix.&#x20;

### `sa-action-*:ns` = ( _namespace_ )&#x20;

All actions support the `:ns` namespace suffix.&#x20;







