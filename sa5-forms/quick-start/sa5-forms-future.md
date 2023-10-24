# SA5 Forms Future



## Expandable Forms

Design concept&#x20;

```
// Some code
<form 
<div wfu-form-expand 
   wfu-form-expand-items-max="n" 
   wfu-form-expand-items-min="m" 
  <div ?wfu-form-expand-item
    <input name="abc"
    blah... blah... blah... 
    <button wfu-form-expand-btn-add
    <button wfu-form-expand-btn-remove
    <button wfu-form-expand-btn-move
  </div>
  <div>
    <button wfu-form-expand-btn-add
  </div>
<div>
```

[https://discourse.webflow.com/t/dynamically-added-form-fields/106444/4](https://discourse.webflow.com/t/dynamically-added-form-fields/106444/4)

* Locate \[wfu-form-expand], iterate&#x20;
* ? Wrap contents
* Duplicate to achieve min
* Wire buttons add / remove / move
* Add will append one and give focus to the first input?&#x20;
  * Remove ID's&#x20;
  * Renumber and update names
  * Default input&#x20;
* Remove removes and renumbers
  * Separate renumbering algo
* ! Review add/remove scenarios&#x20;
*

On submit;

* Auto-remove blanks?&#x20;

Consider;

* Drag\&drop vs up\&down&#x20;
* Required

This is one of those UX’s that’s a bit different for each client, so it’s tricky to build a one-size-fits-all solution. However the basic approach is to use custom code to duplicate your form sub-section, and then append a suffix to the name `-2`, `-3`, etc.

It gets a bit more complex with e.g. multi-item additions, item removals, more than 1 initial item, item re-ordering, and automatic pre-submit cleanup of empty fields. But other than that if they’re simple input fields this works OK.

I personally prefer to have the script also append `-1` to the initial item names for consistency on the form submit data, and I double-wrap the DIVs for convenience of cloning and counting. I also tend to scrape any ID’s ( Webflow likes to add these automatically to form fields ), because they may confuse scripts.

If you need help and have a specific form design you can show me, DM me with the details and I can give you an estimate.



