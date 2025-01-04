# Accordion Future Plans



Add auto positioning for longer accordions;



## Roadmap&#x20;

| Feature                   | Now                                                                              | Planned                                                                                                                                                                                                                                                      | Considering                                                              |
| ------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| Setup                     | Using DIVs                                                                       |                                                                                                                                                                                                                                                              | Using a Tab Component, with automatic detection                          |
| Modes                     | Single-item mode. One panel open at a time                                       | Multi-item mode. Ability to open multiple items                                                                                                                                                                                                              |                                                                          |
| Orientation               | Vertical or horizontal, defined 100% by your open-state and closed-state classes |                                                                                                                                                                                                                                                              |                                                                          |
| Animations for open/close | None                                                                             |                                                                                                                                                                                                                                                              | Considering some means to support WF Interactions, or else GSAP themes.  |
| Dynamic initialization    |                                                                                  | Select on # or query param, and scroll-to                                                                                                                                                                                                                    |                                                                          |
| Auto-scroll               | None                                                                             | <p>Allow auto-scrolling when an accordion opens, so that the top of the new panel is visible.<br><a href="https://discourse.webflow.com/t/dropdown-accordion-behavior/300142/7">https://discourse.webflow.com/t/dropdown-accordion-behavior/300142/7</a></p> |                                                                          |

## JavaScript API

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







