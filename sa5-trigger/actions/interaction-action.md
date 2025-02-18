---
description: Invoke a Webflow Interaction as an SA5 Action
---

# Interaction Action

**Webflow's interactions are powerful, but they are not easily triggered from JavaScript.** &#x20;

`lick`, with the element also configured as a click trigger for a Webflow interaction.&#x20;

## Example&#x20;

Trigger;

```
<a wfu-trigger-click="my-event">Click me</a>
```

Action;

```
<button wfu-action-click="my-event">Hidden button</button>
```

In Webflow's current Interactions ( IX2 ), the button would then be set as a click trigger to trigger the interaction.&#x20;







In IX2, this is setup as a script click event, on a click-based Interactions Trigger.&#x20;

In Webflow's current Interactions ( IX2 ), the button would then be set as a click trigger to trigger the interaction.&#x20;











