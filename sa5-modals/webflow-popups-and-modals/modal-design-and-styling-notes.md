# Modal Design & Styling Notes

## Pro Tips

### Best Practices for Responsive Design

Set the width of the modal element as you want it to appear for each breakpoint. &#x20;

Set a max-height on the content part to support scrollable content.&#x20;

{% hint style="info" %}
For modal sizing you can use most units, e.g. `px`, `vh`, `vw`, `svh`, `svw`, `dvh`, `dvw` units, but avoid `%`.  The modal will be wrapped in a hidden container for layout purposes so % widths will be measured from the container, not the page.&#x20;
{% endhint %}

Consider styling the scrollbar.&#x20;

### Designer Accessibility&#x20;

If the modal is only on one page, you can place your modal(s) at the bottom of the page.

Wrap it in an "admin DIV" and set the DIV to display: none.&#x20;

When you want to edit the modal content, simply change the DIV to display: block, and you'll see the content.&#x20;

If the modal is on multiple pages,&#x20;

* Make it a component
* Place the component in an "admin div"&#x20;

If your clients will be editing the modal in the designer;&#x20;

Place the modal component on a Style Guide page.  Since it is not wrapped in the "admin DIV" there, it will be visible and editable.&#x20;

If your clients will be editing the modal using the Content Editor;&#x20;





### Style Guide Page

Making modals accessible and editable is important, and one of the best ways to do this is to use a Style Guide page.&#x20;

{% hint style="info" %}
It's common to make Style Guide pages draft, so that they are not published as part of the site and do not appear in SERPs- however this (??) makes them difficult to access in the Content editor (verify??).  Instead, you can password protect them.&#x20;
{% endhint %}



Create a&#x20;

If you are tur

* Put your entire modal including the frame in a component, hidden&#x20;
* Put that comp

If your clients use the Content Editor, rather than the designer, you can make the modal accessible to them by;

* Create a Style-guide folder
  * Password protect it
* In it, create pages for the main stylistic elements of your site, e.g. Blog page, Modals, etc.&#x20;
* Drop your modal components on the modals page&#x20;

## Scroll Bars

If your modal may contain too much content to display, especially on mobile devices, we recommend that you add a scrollbar to the `modal_content` class in our design ( see the cloneable ).&#x20;

This can be best done by adding a custom property of `overflow-y: scroll`  &#x20;

{% hint style="info" %}
Custom properties are custom styles at the bottom of the style panel, which allow you to apply specialized CSS to your element.  They are different from custom attributes, and not related to component properties. &#x20;
{% endhint %}

You can custom-style the scrollbar elegantly;&#x20;

```html
<style>
    :root {
      --sa5-modal-scrollbar-color: #188fd6; /* Define the scrollbar color variable */
    }

    /* Custom scrollbar styling for WebKit browsers */
    .modal_content::-webkit-scrollbar {
      width: 12px; /* Width of the scrollbar */
    }

    .modal_content::-webkit-scrollbar-track {
      background: transparent; /* Transparent track for rounded corners to show */
    }

    .modal_content::-webkit-scrollbar-thumb {
      background-color: var(--sa5-modal-scrollbar-color);
      border-radius: 6px; /* Match the div's border radius */
      border: 3px solid var(--sa5-modal-scrollbar-color); /* Padding to inset the scrollbar */
    }

    .modal_content::-webkit-scrollbar-thumb:hover {
      background-color: #1e90ff; /* Slightly darker blue on hover */
    }

    /* Firefox scrollbar styling */
    .modal_content {
      scrollbar-width: thin;
      scrollbar-color: var(--sa5-modal-scrollbar-color) transparent;
    }
</style>
```
