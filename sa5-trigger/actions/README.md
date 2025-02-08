# Actions 🧪



## Element-Level Actions

These actions are generally defined using custom attributes.&#x20;

| Action      | Description                                          | Example uses                                   |                                                                                                     |
| ----------- | ---------------------------------------------------- | ---------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Click       | Fire a click event from script to trigger an element | Click a button, submit a form, switch tabs...  | `wfu-action-click`                                                                                  |
| Interaction |                                                      |                                                | `wfu-action-click`, with the element also configured as a click trigger for a Webflow interaction.  |
| Script      | Invoke a script, or function                         | wfu-action-script                              |                                                                                                     |
| Function    | Invoke a function                                    | wfu-action-function = fun                      |                                                                                                     |



## Page-Level Actions&#x20;

These actions are generally defined by an SA5 Configuration Block;&#x20;

| Action   |                             |   |
| -------- | --------------------------- | - |
| Navigate |                             |   |
| Script   | nvoke a script, or function |   |
|          |                             |   |





Defined a timer as a trigger&#x20;



```html
<script type="application/sa+json" handler="Action.Script">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ScriptAction",
  "@version": "0.1",
  "timer": "60", 
  "timerRepeat": "120",
  "event": "my-event" 
}
</script>
```































