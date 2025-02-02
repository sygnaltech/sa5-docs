# Triggers





| Trigger          | Type      |                                                             |
| ---------------- | --------- | ----------------------------------------------------------- |
| Click            | Manual    | Defined on any button, link, or other element               |
| Timer            | Automatic | Configured in seconds                                       |
| Scroll Position  | Automatic | Configured for a specific page % or a specific px position  |
| Scroll into View | Automatic | Tied to an element                                          |
| Exit Intent      | Automatic | When the mouse moves outside of the page canvas             |





Types;&#x20;

* Manual triggers are user-actioned. These can be configured to ignore modal suppression even if it has already been closed.&#x20;
* Automatic triggers will only open the modal if it is un-suppressed.&#x20;

Suppression;







Goals;

* Timed open, in ms
  * Auto unhide
  * Or, click trigger, for interaction
  * Respects suppression setting
* Triggered open, by scroll
* Triggered open, by exit intent&#x20;
* Timed close, in ms
  * Element removal
  * Or, click trigger, for interaction
  * ? Option to suppress



