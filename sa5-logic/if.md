---
description: Dynamically show and hide elements on your page based on user actions
---

# If ❺🧪

Current;

* Display elements conditionally depending on an eval expression
* Provide the data needed for the eval in the context of the IF wrapper element
* Work with collections lists&#x20;
* Works inside of components&#x20;

Future;

* ? Conditional styling and classes
* ? Conditional IX2&#x20;
* Functional evals&#x20;
* ? Implicit eval vars
  * Current lang
  * Time
  * Geo
  * etc.&#x20;

{% hint style="danger" %}
This feature is not yet available to the public.&#x20;
{% endhint %}

## Use Cases

Hide or show elements conditionally.

Show one of several elements, depending on the IF input params.&#x20;

{% hint style="success" %}
This supports CMS-driven use cases also. Both the parameter inputs for evaluation, and the evaluations themselves, can be stored in the CMS and attribute-bound.&#x20;
{% endhint %}

## Usage Notes

### Define your dynamic elements

To the elements you want to dynamically show and hide, add these attributes;

#### `wfu-logic-if`

Place this on the outer element that contains your elements to be evaluated for conditional display.

#### `wfu-logic-param-*` = ( value )

Place this on the same element that has `wfu-logic-if`.&#x20;

These parameters define the "inputs" that you can use in your evaluation statements. The `*` represents the name.&#x20;

e.g. `wfu-logic-param-startweek` here the param is named `startweek`.&#x20;

e.g. `wfu-logic-param-end_week` here the param is named `end_week`. &#x20;

{% hint style="warning" %}
**IMPORTANT**\
The param name portion must be all lowercase, but may contain underscores.  `startweek` and `start_week` are OK, `startWeek` is not.&#x20;
{% endhint %}

{% hint style="info" %}
Typically you will bind this attribute to a CMS field or component property, so that the data is dynamic.&#x20;
{% endhint %}

#### `wfu-logic-if-display` = ( eval statement )

Here's the magic. You can use simple JS evaluation statements to control display.

For example, suppose you have two params defined, `startweek` and `endweek`. You have four elements that you want to conditionally display...

* One if both `startweek` and `endweek` have values
* One if both `startweek` and `endweek` are blank
* One if `startweek` is defined, but `endweek` is blank
* One if `startweek` is blank, but `endweek` is defined

In a component, there is no conditional visibility built in, so this make it possible to create a similar capability using JS.&#x20;

On each of those four elements, you can define the eval rule that defined when it should be displayed, to wit;&#x20;

* One if both `startweek` and `endweek` have values
  * `wfu-logic-if-display` = `startweek && endweek`
* One if both `startweek` and `endweek` are blank
  * `wfu-logic-if-display` = `!startweek && !endweek`
* One if `startweek` is defined, but `endweek` is blank
  * `wfu-logic-if-display` = `startweek && !endweek`
* One if `startweek` is blank, but `endweek` is defined
  * `wfu-logic-if-display` = `!startweek && endweek`

### Evaluation Statement Syntax&#x20;

You can combine standard formula symbology such as parenthesis, not ( ! ), and ( && ) and or ( || ). For example;&#x20;

* price >= 10000
* product\_name = 'sale'

## Advanced Usage Notes

Any JS eval function will work, which means you can likely use window variables and other conditions beyond the data set ( untested ).&#x20;











