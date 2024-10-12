# Video Controller File Format

## Triggers&#x20;



```
15:46 event1
23:14 event2
40% event 3
90% show-button
```



## Event Types&#x20;

### Custom Event

Fires a custom event which is captured by the Video Controller handler. Your code can then do whatever it wants.&#x20;





## Considering

### Gate Event

Stop, and require;

* Form fill, e.g. email address capture &#x20;
* Acceptance button&#x20;
* Payment&#x20;

### Player Rules

Player UX changes;&#x20;

* Can pause
* Can stop
* Can seek
*





```
wfu-video name

wfu-video-config name 
{
  [
    {} 
  ]
}

```



## Tie to States

Trigger another state change, which ties to other UX behaviors







wfu-vis

default course-locked course-unlocked

vitzflow reseller

states by zone site state page state user state section state

Boolean states progression states state engines change state ( can reject )



















