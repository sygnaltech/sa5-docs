---
description: Intelligent, script-driven switching of a content area.
---

# Switch Case ❺🧪

{% hint style="danger" %}
**NOT YET AVAILABLE**&#x20;

Internal R\&D only.&#x20;
{% endhint %}

**Think tabs, but more versatile.**&#x20;

SA5's Switch Case is a modeled on the programming concept of the same name;

```javascript
switch(x) {
  case 'item1': {
    console.log("item1 selected.");
    break;
  }
  case 'item2': {
    console.log("item2 selected.");
    break;
  }
  default: {
    console.log("no matching item found.");
    break;
  }
}
```

Here we have a series of defined case value.  When this block is evaluated;

* if x = 'item1', then we'll get the message _item1 selected_.&#x20;
* if x = 'item2', then we'll get the message _item2 selected_.&#x20;
* if x = 'item3', or any other value, then we'll get the message _no matching item found_.&#x20;

This simple concept adapts well to a number of UX concepts that already exist in Webflow;

* Tabs&#x20;
* Sliders&#x20;
* Forms, with the form, success, and error messages&#x20;
* Conditional visibility blocks&#x20;

**Think of it as dynamic conditional visibility.**&#x20;

{% hint style="success" %}
**EXPERIMENTAL** \
This will likely be most useful in SA6 if reactive techniques are included.&#x20;
{% endhint %}





## Basic Usage Notes

Here's an example setup;&#x20;

```html
<div wfu-switch="my-switch">
  <div wfu-switch-case="item1">
     ... some content ... 
  </div>
  <div wfu-switch-case="item2">
     ... some content ... 
  </div>
  <div wfu-switch-case="?">
     ... some default content ... 
  </div>  
</div>
```

## Switch Attributes&#x20;

### wfu-switch = ( _switch-name_ )&#x20;

**Required.** Defines the switch block. Place on the outer switch DIV.&#x20;

Set to a unique name, to identify this switch block.

### wfu-switch-match = ( _match-type_ ) &#x20;

One of;&#x20;

* `default` ( _default_ ) - Use the default case matching rules.&#x20;

### wfu-switch-display = ( _display-type_ )&#x20;

**Optional.** Specify a display type you want the case elements to be displayed in.&#x20;

* `block` ( default )&#x20;
* `flex`&#x20;
* `grid`&#x20;
* `inline-block`&#x20;
* `contents`&#x20;

{% hint style="warning" %}
**TECHNICAL TEAM NOTE** &#x20;

This attribute may not be needed in the final implementation, since we may use `style` tags.&#x20;
{% endhint %}

## Switch Case Attributes &#x20;

### wfu-switch-case = ( _case-name_ )

**Required.** Defines a case block. Place on an immediate child DIV of the `wfu-switch`.&#x20;

Set to the value you want to match. When your switch is triggered by script, or on page load, or by an SA5 event, a case div that matches the specified value will display, and a case div that does not match the specified value will hide.&#x20;

{% hint style="success" %}
When the case-name is set to a **question-mark ( `?` )**, this is handled as a special default case. This item will be shown when there are no other matches.&#x20;
{% endhint %}

Using the above example,

e.g. switching to "item1" will show the first item only

e.g. switching to "item3" will show the last item only, as there were no matches and it's the default &#x20;

## Advanced Usage Notes

Here's a more advanced example setup;&#x20;

```html
<div wfu-switch="my-switch-2">
  <div wfu-switch-case="item1,item3">
     ... some content ... 
  </div>
  <div wfu-switch-case="item2,item3">
     ... some content ... 
  </div>
  <div wfu-switch-case="?">
     ... some content ... 
  </div>  
</div>

... some content ...

<div wfu-switch="my-switch-2">
  <div wfu-switch-case="item1">
     ... some content ... 
  </div>
  <div wfu-switch-case="item2,?">
     ... some content ... 
  </div>
</div>
```

Note;

* We have multiple separate switch blocks with the same name.&#x20;
* Case items can have comma separated values&#x20;
* Values can be repeated across case items&#x20;
* Case default can exist multiple times, and on elements that also have case&#x20;

Using the above example,

e.g. switching to "item1" will show items 1 & 4&#x20;

e.g. switching to "item3" will show items 1 & 2&#x20;

e.g. switching to item8 will show items 3 and 5 ( which have defaults ) &#x20;

## Designer Experience

To create the best experience in the designer, it's often effective to hide all case items on the page but show them all in the designer.&#x20;

You can use this as a custom HTML embed.&#x20;

```html
<style>
[wfu-switch-case] {
  display: none;
}
html:not([data-wf-domain]) [wfu-switch-case] {
  display: block;
}
</style>
```



## Future

Make it Reactive, so that a variable value change would change the&#x20;

When placed on a Tabs element, behave differently?&#x20;

When placed on a Slider element, behave differently?

When placed on a Form element, behave differently?&#x20;















