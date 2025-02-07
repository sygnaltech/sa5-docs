---
description: Complex grid layouts
---

# Equal Height Rows ❺🧪



## Equal Height Rows

Goals;

* Support equal-height rows&#x20;
* Make it responsive, so that this calculation is only performed on specific breakpoints&#x20;
* Can be applied to any element, the children will be considered rows
  * Does not explicitly need to be a grid&#x20;



* Mobile view?&#x20;



## Technical Notes

Approaches;&#x20;

Calc

* Identify all grids with same name&#x20;
* Determine largest row height of each, per item, and adjust others
  * Apply as style height&#x20;
* Must re-adjust on any resize&#x20;
* Must remove on breakpoints where we do not want this&#x20;

Subgrid

* Must set rows of parent grid based on child grid max?&#x20;
* Must suppress collection list layout elements of child grids to allow alignment&#x20;

Set rows&#x20;

Layout to Grid ( move elements )&#x20;





`wfu-grid-equalheightrows` = ( name )

All elements with the matching name will be set as equal height rows&#x20;

Missing elements?  Create, ignore&#x20;







\``wfu-grid-equalheightrows:bp` = ( breakpoints )&#x20;



d,t











Process&#x20;







