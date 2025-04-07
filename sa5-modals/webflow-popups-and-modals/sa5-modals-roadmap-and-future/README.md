# SA5 Modals Roadmap & Future

## ESC key support

[https://discourse.webflow.com/t/escape-key-working-only-on-the-first-cms-modal-but-not-the-others/280010/6](https://discourse.webflow.com/t/escape-key-working-only-on-the-first-cms-modal-but-not-the-others/280010/6)

Non-closeable modal&#x20;



## Template Modals&#x20;

Pulling content from another source, as specified from the trigger;

wfu-modal-content = ( content-name )



wfu-modal-content-area &#x20;



##

##

## Roadmap

| Feature                             | Short Term                                                                                                        | Medium Term                                                                                                                                                                                                                                    | Future                                                                                                                                                                   |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Modal setup in the Webflow designer | 2 DIVs                                                                                                            | Possibly only 1 DIV, with auto-frame generation                                                                                                                                                                                                |                                                                                                                                                                          |
| Modal type                          | <ul><li>Popup. Easily closed.</li></ul>                                                                           | <ul><li>Modal. Only a specific action can close. </li></ul>                                                                                                                                                                                    |                                                                                                                                                                          |
| Content source                      | <ul><li>Static content</li></ul>                                                                                  | <ul><li><p>CMS content</p><ul><li>Named with zones</li></ul></li></ul>                                                                                                                                                                         | <ul><li>IFRAME</li><li>External source e.g. Google Doc</li></ul>                                                                                                         |
| Modal frame styling                 | <ul><li>Borders</li><li>Corners</li><li>Padding</li><li>Shadows</li><li>Background</li><li>Transparency</li></ul> | <ul><li>Possible themes</li></ul>                                                                                                                                                                                                              |                                                                                                                                                                          |
| Content admin                       | <ul><li>Designer</li><li>Content editor</li></ul>                                                                 |                                                                                                                                                                                                                                                |                                                                                                                                                                          |
| Triggers ( open )                   | <ul><li>Trigger element click</li></ul>                                                                           | <ul><li>Timed trigger</li><li>Trigger element scroll-into-view</li><li>Page scroll to %</li><li>Exit intent</li><li>Link triggers using SA5's <code>##link</code> standard capability </li></ul>                                               | <ul><li><p>JS</p><ul><li>SA5 booking lib</li></ul></li><li>Cookie exist / not-exist</li><li>URL formation e.g. <code>#book</code> </li><li>Adblocker detection</li></ul> |
| Triggers ( close )                  | <ul><li>Close button ( auto )</li><li>Close button ( manual )</li><li>External close trigger click</li></ul>      | <ul><li>Timer</li><li>ESC key</li><li><p>Successful form submission</p><ul><li>Delay? thanks... close</li></ul></li></ul>                                                                                                                      | <ul><li>% Page scrolling?</li><li>Programmatic triggers, like an over 18 that checks birthdate calc </li></ul>                                                           |
| Suppression                         | Defined at the modal level                                                                                        | <ul><li>Possibly add sessionStorage as a suppression mechanism</li><li>Form submit suppression on success only</li></ul>                                                                                                                       | <ul><li>Possibly button-specific suppression ( for "never show again" )</li></ul>                                                                                        |
| Scrolling                           | Manually defined at the modal level via custom CSS chunk                                                          | <ul><li>Attribute with basic scrolling behaviors</li><li><p>Basic scrollbar style attributes</p><ul><li>thin-black</li></ul></li></ul>                                                                                                         |                                                                                                                                                                          |
| Sizing                              | <ul><li>Defined at the modal frame level, responsively</li><li>Min size, max size</li></ul>                       |                                                                                                                                                                                                                                                |                                                                                                                                                                          |
| Positioning                         | Centered                                                                                                          | 9 positions                                                                                                                                                                                                                                    |                                                                                                                                                                          |
| Animation on open / close           | Simple predefined                                                                                                 | <ul><li>slide in/out + direction</li><li>grow/shrink</li><li>fade in/ out</li></ul>                                                                                                                                                            | <ul><li>WF Interactions</li></ul>                                                                                                                                        |
| Overlay                             | <ul><li>Simple predefined styling</li><li>Click triggers close</li></ul>                                          | <ul><li><p>Themes</p><ul><li>gray</li><li>glass</li><li>blur</li></ul></li></ul>                                                                                                                                                               | <ul><li>Customizable ( as an element? )</li><li>Ability to suppress click on close</li></ul>                                                                             |
| Timing                              | <ul><li>None</li></ul>                                                                                            | <ul><li><p>Schedule</p><ul><li>Start / end dates</li><li>Weekdays</li><li>Hours of the day</li></ul></li></ul>                                                                                                                                 | <ul><li>Allow invocation override by a trigger to force show outside of scheduled times</li></ul>                                                                        |
| Competition                         | <ul><li>None? </li></ul>                                                                                          | <ul><li>Restrict to a single modal open at a time</li><li>Auto close any prior modal if a new modal is open</li><li>Modal queue?  Show sequentially. </li><li><p>Prioritization</p><ul><li>High</li><li>Medium</li><li>Low</li></ul></li></ul> | <ul><li>Non-critical v. critical- auto suppress non-critical if another has shown</li></ul>                                                                              |
| Page behavior                       | <ul><li>None</li></ul>                                                                                            | <ul><li>Support no-scroll on page content behind the modal</li></ul>                                                                                                                                                                           | <ul><li>Support scrolling as a trigger to close the modal</li></ul>                                                                                                      |
| Analytics                           | <ul><li>None</li></ul>                                                                                            | <ul><li>GTM</li></ul>                                                                                                                                                                                                                          |                                                                                                                                                                          |
| Modal namespaces                    |                                                                                                                   | <ul><li>Likely to add for CMS-driven modal support </li></ul>                                                                                                                                                                                  |                                                                                                                                                                          |

## Advanced Notes&#x20;

### Controller Integration

On open, close, etc, the modal or triggers invoke the action and the modal is the first responder, however the controller is informed and queried on some actions.&#x20;

For example, a modal opening at 5000ms and then a different one opening at 8000ms might not be legit.  Or a modal opening on a timer, and then a scroll trigger, and then an exit-intent trigger...&#x20;



### Multi-Function Modals

Buttons which perform an action and also close the modal?&#x20;

* Submit an email form&#x20;
* Accept terms
* Confirm 18, etc.&#x20;

### Open / Close Animations

* default show
* grow from a point
* slide in right
* slide in left
* slide in bottom
* slide in top
* spin in right
* fade in
* random, or a list of random CSV options

## Future&#x20;

( modal-name ) | ( zone.modal-name )

**name** will target the first modal found with that name in the page.

**zone.name** will target the first modal found with that zone and name in the page

`wfu-modal-target-zone` = ( zone )

This is a convenience to separate the zone from the name. It's most oftenly used when the name is bound to a CMS slug, and the one needs to group those items separately from other modals in the page.&#x20;

### Modal appearance options

Scroll freeze option&#x20;

Sound FX&#x20;

### Buttons? &#x20;

For OK close separate from e.g. hyperlinks or other actions

Cancel?&#x20;

Allow user to create these, or we default add a button?&#x20;

Lets us separate content from popup

modal-button

modal-button-class

### Support for Forms

wfu

### Callback

On OK, Cancel&#x20;



Things we're considering;

JS API;

* Invoke, suppress modal from script
* Open event, close event&#x20;



## a11y&#x20;



## Native HTML elements&#x20;

Consider using internal HTML \<dialog> element&#x20;

[https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)











