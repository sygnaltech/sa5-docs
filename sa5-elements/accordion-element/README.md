# Accordion Element

An **accordion** element is a common user interface ( UI ) component used to organize and manage pieces of content in a structured, compact and user-friendly way. It is named "accordion" because it functions similarly to the musical instrument of the same name, where sections can expand and collapse, revealing or hiding content.

{% hint style="success" %}
In Sygnal's SA5 implementation, the accordion is in the same family of UX's as a tab component or a slider, and we collectively refer to these as "deck elements".  It is also not based on a native Webflow element and is instead&#x20;
{% endhint %}

## Use Cases

* **Content Organization:** Accordions are particularly useful for organizing large amounts of information into digestible chunks. For example, they are often used in FAQs, where each question expands to reveal the answer.
* **Forms and Surveys:** They can be used to break down lengthy forms into manageable steps or sections, improving the user's ability to focus on one task at a time.
* **Mobile Design:** In responsive design, accordions are helpful in presenting content on small screens, where space is limited.

## Goals

* No interactions dependencies
* Easy designer setup
* Good designer view
* Strong programmatic control
  * Ability to tell when a new panel has opened&#x20;
  * Ability to change the open panel programmatically&#x20;

## Element Structure

Structure;

Accordion

Item ( aka. panel / section )

Header

Content



Because accordions are a card deck UX, they use use SA5's card deck controller interface for the JS API ( first, last, next, prev, open item #... )

##

Future;

* Possible use of interactions for open and close transitions&#x20;

## Design

To keep everything easily managed and controlled within the designer, SA5's accordion uses the addition and removal of classes to control the open and closed states. This gives you the ability to define what open state looks like and what closed state looks like, all within the designer.&#x20;

## Usage Notes

Structure;&#x20;

wfu-accordion = name

wfu-accordion-item = name optional&#x20;

wfu-accordion-item-tab

wfu-accordion-item-content

### Classes

Allows you to specify the classes to add and remove from the structural elements, to represent the open and closed states.

Place these directly on the Accordion outer element itself.&#x20;

wfu-accordion-class-open&#x20;

Default is `is-open`

wfu-accordion-class-closed

Default is `is-closed`



wfu-accordion-item-trigger

* open -&#x20;
* close -&#x20;





Initial state&#x20;

First open? Defined by classes ( they will be removed later )&#x20;





Transition

Closing transition, Opening transition, pre-set&#x20;



Interaction to open  trigger button on that panel

Interaction to close  ( call on currently open one only )

## Events

### accordionChanged

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['accordionChanged', 
  (accordion, index) => {
    
    console.log("ACCORDION CHANGED", accordion.name, accordion, index); 

    switch(accordion.name) {
      case "demo1": 
        // An accordion was clicked in the Demo 1 accordion element
        // index indicates which tab was clicked ( 0-based )
        break;
      case "demo2": 
        // An accordion was clicked in the Demo 2 accordion element
        // index indicates which tab was clicked ( 0-based )
        break;
    }

  }]); 
</script>
```







