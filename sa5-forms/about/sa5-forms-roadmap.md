# SA5 Forms Roadmap

## Elements

| Element       | Type                          | Status | API                                           |
| ------------- | ----------------------------- | ------ | --------------------------------------------- |
| Input         | Extend native Webflow element |        |                                               |
| Checkbox      | Extend native Webflow element |        |                                               |
| Radio Button  | New element                   |        |                                               |
| Button        | Extend native Webflow element |        |                                               |
| Option        | Extend native Webflow element |        |                                               |
| Radio Button  | Extend native Webflow element |        |                                               |
| Range Input   | New element                   |        | Modes, e.g. 0-n, n-m, star rating, increments |
| Date Input    | New element                   |        |                                               |
| Numeric Input | New element                   |        |                                               |
| Phone Input   | New element                   |        | International options                         |

## Advanced Forms Validation

Multi-Step Forms

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







