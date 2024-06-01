---
description: Styling SA5's Autocomplete Element
---

# Styling

SA5's Autocomplete element is highly styleable.

## Input Styling

* Style the input and dropdown indicator icon
* Set placeholder text in your input element as a hint for how to use the element on your site

## Dropdown Styling

* General styling like rounded corners and background color
* Scrollbar styling
  * Visible only when needed

## Dropdown Item Styling

Style the list items any way you want;

* Hover styling
* Add icons
* Support multiple parts, such as pricing indicators

{% hint style="success" %}
To make more complex layouts, use a Link block rather than a Dropdown Link element, so that you can arrange contents within it.&#x20;
{% endhint %}

## Examples

<figure><img src="../../.gitbook/assets/autocomplete.webp" alt=""><figcaption><p>The example on <a href="https://www.sygnal.com">Sygnal's homepage</a> uses a custom scrollbar an a cimply-styled input with the dropdown carat positioned over the input element. </p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (51).png" alt=""><figcaption><p>Add icons, and style the Site Search element specially.  </p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (50).png" alt=""><figcaption><p>Add multiple parts within your items from your collection list, such as pricing. </p></figcaption></figure>



## Scrollbar Styling

The list scrollbar can be made more attractive on most browsers by applying some custom CSS.  Adjust as desired.&#x20;

{% hint style="info" %}
Here, we've given the Dropdown List element a class of `service-find_dropdown-list`.  Change the CSS selectors below to match whatever class you give yours.&#x20;
{% endhint %}

{% code overflow="wrap" %}
```css
    /* Custom scrollbar styling for WebKit browsers */
    .service-find_dropdown-list::-webkit-scrollbar {
      width: 12px; /* Width of the scrollbar */
    }

    .service-find_dropdown-list::-webkit-scrollbar-track {
      background: transparent; /* Transparent track for rounded corners to show */
    }

    .service-find_dropdown-list::-webkit-scrollbar-thumb {
      background-color: dodgerblue;
      border-radius: 6px; /* Match the div's border radius */
      border: 3px solid dodgerblue; /* Padding to inset the scrollbar */
    }

    .service-find_dropdown-list::-webkit-scrollbar-thumb:hover {
      background-color: #1e90ff; /* Slightly darker blue on hover */
    }

    /* Firefox scrollbar styling */
    .service-find_dropdown-list {
      scrollbar-width: thin;
      scrollbar-color: dodgerblue transparent;
    }
```
{% endcode %}
