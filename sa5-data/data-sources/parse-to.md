---
description: Convert Rich Text into a datasource, based of certain profile rules
---

# RichText Data Source 🧪

{% hint style="success" %}
**REQUEST FOR COMMENT ( RFQ )** \
This SA5 feature is in the RFQ stage. We're [gathering community feedback](https://sygnal-attr.discourse.group/t/sa5s-richtext-data-source-is-open-for-comment/1103) in the forum and will consider the implementation details here before we progress.&#x20;
{% endhint %}

In certain specific scenarios, site designs need a convenient content source with the following shape;&#x20;

* A title&#x20;
* A rich text chunk
  * with support for images, videos, lists, etc.  &#x20;

We would then use this list of chunks to create an accordion FAQs section as part of a blog article, or a set of tabs in a lesson section.&#x20;

{% hint style="info" %}
Webflow supports this type of construction through the use of multirefs, where you could create a separate FAQs collection and then link to them.  However we find this very difficult and inconvenient for clients to admin. Ordering is not implicit, and the new item-specific CMS publishing makes these types of constructions very difficult to work with on the canvas.&#x20;
{% endhint %}

## Goals&#x20;

* Full static content and CMS compatibility &#x20;
* Simple administration, easy for clients to understand&#x20;
  * Easy to add/remove&#x20;
  * Easy to re-order content. These chunks need to be orderable so that the content admin can give them a specific sequence. &#x20;
  * Easy access. Ideally, the entire set of chunks would be stored within a CMS item, so that they are directly and explitly part of a blog or article.&#x20;
* Flexible in its ability to apply to certain UX scenarios&#x20;

## Use Cases

Here are some examples of specific UX's we currently have in mind as target use cases to support;&#x20;

* FAQs. A serious of accordions presented with a title, and expandable accordion and a content area.
* Tabs. A serious of dynamic tabs with simple rich text content, easy to order

And possibly...&#x20;

* Footnotes. In a large blog or news article, the ability to define footnotes as content that is directly attached to the Blog entry. &#x20;

## Technical Concept&#x20;

One of the most appealing approaches we've considered is to leverage Webflow's rich text element and use Headings as the item-separating mechanic.&#x20;

* The entire set of **titles** and **rich text chunks** would be stored in a single rich text field or element.&#x20;
* Headings like H1, H2, H3, etc. would be processed as the separator and the title, and content in-between headings would be processed as rich text content&#x20;
  * By default, delineation would occur at all headings, however we may allow for a heading level, e.g. H1's and H2's denote the start of a chunk, H3's+ are part of an item's rich text content.&#x20;

## Rendering&#x20;

The idea then would be to use this shaped datasource as a source for an SA5 Repeater lib, which can then pull and bind those content pieces.&#x20;

## Related Ideas&#x20;

It may be beneficial to support other rich text-source parsers;

* Parse all media only, including images, video, multimedia&#x20;
  * Including captions&#x20;
* Generate a mixed-media lightbox or gallery&#x20;

Or;

* Parse lists and use as list content
* Parse paragraphs and use as list content&#x20;



