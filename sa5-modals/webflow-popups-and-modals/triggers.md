# Triggers





<table><thead><tr><th width="202">Trigger</th><th>Type </th><th></th></tr></thead><tbody><tr><td>Click </td><td>Manual</td><td>Defined on any button, link, or other element </td></tr><tr><td>Timer</td><td>Automatic</td><td>Configured in seconds </td></tr><tr><td>Scroll Position 🧪</td><td>Automatic</td><td>Configured for a specific page % or a specific px position </td></tr><tr><td>Scroll into View 🧪</td><td>Automatic</td><td>Tied to an element</td></tr><tr><td>Exit Intent 🧪</td><td>Automatic</td><td>When the mouse moves outside of the page canvas </td></tr></tbody></table>





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



