---
description: Improve the Design-Time Experience when working with SA5.
---

# Webflow Designer Support ❺

The Webflow Designer cannot execute custom code, or external CSS, which means that the design-time experience can&#x20;

Most especially I see these when;

* You have a long collection list of items that will be filtered in the published view.&#x20;
* You have modals or other elements that won't always appear

## SA5's Design-Time Support

Fortunately, you can adjust the design-time view using an HTML Embed with custom CSS.&#x20;

Set that up any custom CSS embeds you want, and if you add the \[wfu-design] custom attribute to them, SA5 will remove them automatically as soon as any of the libraries load.&#x20;

#### Hide an element at design-time;

```html
<style>
.modal1 {
  display: none
}
</style>
```

#### Reduce a collection list to just a few items of display;

For a collection list with the ID `my-list`, let's display the first 3 items in the designer only.&#x20;

```html
<style>
/* By default, hide all .w-dyn-item elements inside #my-list */
#my-list .w-dyn-item {
    display: none;
}

/* Display the first three .w-dyn-item elements inside #my-list */
#my-list .w-dyn-item:nth-child(1),
#my-list .w-dyn-item:nth-child(2),
#my-list .w-dyn-item:nth-child(3) {
    display: block; /* or display: flex, inline-block, etc., depending on your layout */
}
</style>
```





