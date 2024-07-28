# Modal Design Notes

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
