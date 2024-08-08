# Accordion Element



Structure;

Accordion

Item

Tab

Content



Because accordions are a card deck UX, they use use SA5's card deck controller interface for the JS API ( first, last, next, prev, open item #... )

## Goals

* No interactions dependencies
* Easy designer setup
* Good designer view

Future;

* Possible use of interactions for open and close transitions&#x20;

## Design

To keep everything easily managed, SA5's accordion uses the addition and removal of classes to control the open and closed states.&#x20;

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









