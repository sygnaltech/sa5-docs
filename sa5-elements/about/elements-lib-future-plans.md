# Elements Lib Future Plans



## Elements

| Element                 | Type                          | Status   | API  |
| ----------------------- | ----------------------------- | -------- | ---- |
| Tabs                    | Extend native Webflow element | Released | Deck |
| Slider                  | Extend native Webflow element | Released | Deck |
| Deck Controller         | New element                   | Released |      |
| Button                  | Extend native Webflow element | Released |      |
| Dropdown                | Extend native Webflow element | Released |      |
| Lightbox                | Extend native Webflow element | Released |      |
| Radio Button            | Extend native Webflow element | Released |      |
| Autocomplete            | New element                   | Released |      |
| Accordion               | New element                   | Beta     | Deck |
| Stacked ( like Tinder ) |                               |          | Deck |

## JavaScript API&#x20;

Key objectives...

* We ideally want similar elements to share the same API
  * So that they can be swapped easily&#x20;
  * Especially Deck-based elements
* Base API
  * Enable / Disable
  * ScrollTo
  * Initialize
  * Clone ?&#x20;
* Easy integration and extension into TypeScript projects, especially [Sygnal Site Engine ( SSE )](https://engine.sygnal.com).

### Methods&#x20;

| Feature                       | Now                                                   | Planned | Considering                  |
| ----------------------------- | ----------------------------------------------------- | ------- | ---------------------------- |
| Programmatic Navigation       | Navigate to slide number, first, last, next, and prev |         | <p>nextLoop <br>prevLoop</p> |
| Add / remove / reorder slides |                                                       |         | Considering                  |

### Events

| Feature               | Now                        | Planned                                                                              | Considering |
| --------------------- | -------------------------- | ------------------------------------------------------------------------------------ | ----------- |
| Item changed event    | Occurs on any slide change | Will reconsider how this should work in multi-item mode                              |             |
| Item can change event |                            | Can open, can close, etc.  Give dev the ability to reject an open or close request.  |             |







