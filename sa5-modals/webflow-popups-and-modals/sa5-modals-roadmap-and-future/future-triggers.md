# Future Triggers



{% hint style="info" %}
Some triggers, like timer and exit-intent triggers are defined on the modal directly. Others are defined on separate elements such as button elements.&#x20;
{% endhint %}

SA5 supports both manual triggers automatic triggers. &#x20;

* Manual triggers are intentionally invoked by the user as part of the user flow, and will be invoked even if the user repeats that flow multiple times.
* Automatic triggers occur outside of the user action, and should not occur again if the modal has already been invoked ( manually or automatically ). &#x20;

<table><thead><tr><th width="167">Trigger</th><th width="465">Notes</th><th>Type</th></tr></thead><tbody><tr><td>button</td><td>Triggers the modal when the user clicks on a button or other element that is tagged. </td><td>manual</td></tr><tr><td><del>form</del></td><td>Triggers the modal when the user submits a form.</td><td>manual</td></tr><tr><td><del>timer</del></td><td>Triggers the modal when a timer has elapsed, starting from page load.</td><td>auto</td></tr><tr><td><del>scroll</del></td><td>Triggers the modal when the page has been scrolled x%.</td><td>auto</td></tr><tr><td><del>scrollintoview</del></td><td>Triggers the modal when a certain element is scrolled into view.</td><td>auto</td></tr><tr><td><del>exit</del></td><td>Triggers the modal on exit intent.</td><td>auto</td></tr></tbody></table>

{% hint style="info" %}
Multiple triggers can be applied to the same modal, for example, two button triggers, a timer, and a scroll trigger can all invoke the same modal. To support this, the attributes for each trigger type are discrete ( see below ).&#x20;
{% endhint %}

? Consider trigger once rule&#x20;







