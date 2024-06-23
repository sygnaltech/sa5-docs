---
description: Enhance Richtext capabilities from the ground up
---

# Hyperflow Richtext

Provide all of SA5's RTB capabilities at the ground level.

* Nested lists
* Automated linking
* Automated transforms and embedding

## Components Support

One of the primary issues in embedding components into richtext is the lack of CSS isolation. We may be able to resolve this by;

* Adding the RTB's custom class to all of its sub elements automatically
* &#x20;? ignoring content in Embeds...
* Updating the Webflow-generated CSS file so that RTB/RTE styling only applies to sub-elements within the RTB.

This would make it possible to drop in a component or embed without risk of it being affected by the RTB.&#x20;

&#x20;? Is there a way to mutate CSS classes and proxy the styling of another class&#x20;



&#x20;fixin

Possibly, ad

[https://discourse.webflow.com/t/add-components-to-rich-text-elements-or-collection-items/263655/2?u=memetican](https://discourse.webflow.com/t/add-components-to-rich-text-elements-or-collection-items/263655/2?u=memetican)

Instead of modifying Webflow's CSS, generate and cache a new one. Inject it only into pages with the necessary RTB.&#x20;

Or place it as a style embed, from KV store. &#x20;
