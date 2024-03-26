---
description: Add "smart" elements within your Webflow Rich Text Blocks
---

# Annotations 🧪

{% hint style="danger" %}
**CONCEPTUAL**\
This is a feature set we're considering.
{% endhint %}

## Conceptual Examples

* Hint blocks, such as an info, warning, feature etc.
* Tooltips
* Footnotes
* Buttons

Embedded content? ;

* Tables
  * From Google docs / Google sheets
* Other content
  * Google sheets content&#x20;
* Figma
* Diagrams&#x20;

## Markup

The goal is to use markup within the Rich Text Block editor that is memorable, easily applied, and will not conflict with Webflow's native markdown detection support.

Line items

Indication is places at the start of the line

* e.g. >>&#x20;
* e.g. @&#x20;
* e.g. @@&#x20;
* e.g. =&#x20;
* e.g. ==&#x20;

List items

Within lists, these start-of-line indicators are similar, but can have different meanings

* e.g.

Blockquote annotations

Within blockquotes, these can be used at the start of the blockquote to create a note / hint block

* e.g. ! Alert
* e.g. ? warning
* e.g. # note
* e.g. \~ deprecation note

These should be interpreted, removed, and a class applied. That class should then affect the styling, coloring, and iconography of the blockquote, and be designed on a style guide page.&#x20;

Inline items

* e.g. Footnotes \[1] &#x20;
* \[\[ ]]
* \{{ \}}
* \~\~ strikethrough text&#x20;



