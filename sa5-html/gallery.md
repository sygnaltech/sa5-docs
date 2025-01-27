# Gallery 🧪



{% hint style="info" %}
CONCEPTUAL&#x20;
{% endhint %}



Specialize your grid layouts to create distinctive layouts for;

* Photo galleries
* Blogs
* etc.&#x20;





wfu-gallery

Identifies the gallery

Place this on the collection list central element &#x20;





wfu-gallery-layout



* random
* tiles
*

## Layout Engines

### Tight Collage

wfu-gallery-layout = tight-collage

[https://storytailorapps.com/storytailor-blog/?v=c97b334ffd41](https://storytailorapps.com/storytailor-blog/?v=c97b334ffd41)

* CMS compatible
* Can possibly optimizes portrait and landscape and square orientations

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Approach;

Setup;

* Set the grid to 12 cols, all breakpoints&#x20;
* Set your row height to what you want
* Cover container class for card&#x20;
  * Image
  * Video
  * Other

Layout engine approach;

* Divide images into row groupings&#x20;
  * At mobile landscape+, 2 to 3
    * Avoiding any 1-item rows&#x20;
  * At mobile portrait, we can either shrink everything, or switch to a 1 col view&#x20;
* Responsiveness
  * Breakpoint change triggers
  * Override grid, or forc

Advanced;

* Hinting&#x20;
  * CMS can indicate if the card is portrait, square, or landscape
    * wfu-gallery-item-orientation = portrait | square | landscape
    * We use this to optimize a column config for each set&#x20;



When a client wants a distinctive layout like this, I use a collection list in a grid format, with the grid set to 12 columns.

If your layout were manual- then you could just store a field with the number of columns you want for each tile, and manually arrange them in 12-col rows, e.g. 3+9, 6+6, 4+4+4, 3+6+3… whatever.

Here it sounds like you want it to be automatic which means that you need to custom code a simple layout engine to make those determinations for you and apply those colspans to ensure 12-col rows.

I usually do 2 to 4 images per row at desktop, and 3 to 9 colspan per item, depending. It’s all about simple calcs and building an adaptable layout engine.

Portrait v. Landscape is more difficult, you’re going to end up cropping things regardless. To optimize for it, I use hints, so in the CMS, I’ll indicate for each item whether its tile is portrait or landscape, and the my engine will use those hints to choose the best layout for a row.

Important- there are always sizing and cropping challenges, but there are two techniques you can use to make this work best;

* Have the layout engine first divide your image set into rows, and avoid any 1-item rows. Go for 2 to 3 items per row always, that avoids isolating a portrait image on its own 12-col row, where most of it would be cropped.
* The images you use to represent each of the tiles should ideally always have the visual interest right at the center of the photo.

You’ll definitely need a programmer to build that part, unless you can find a library that already has that encoded. Give me a shout if you need a pro to build this.



[https://discourse.webflow.com/t/blog-collage-like-blogstomp-storytailor/302566](https://discourse.webflow.com/t/blog-collage-like-blogstomp-storytailor/302566)





















