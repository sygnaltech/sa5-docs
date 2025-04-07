# Event Data



In SA5's pub/sub model, certain Actions benefit from data.

* The class adder needs to know what class to add, remove or toggle&#x20;
* Video seeking needs a position to seek to&#x20;

These are specified in the form of Action-specific attributes, such as;

```
sa-event-action-video-seek:pos = 80%
```

{% hint style="success" %}
SA5 convention is to use the specific action attribute name, followed by a colon and the data item name. This makes it mostly-unambiguous and allows us the freedom to have several data items when necessary.&#x20;
{% endhint %}

## Where this is placed&#x20;

In most cases it makes sense to put this on the Action element directly so that it is centrally controlled no matter what trigger was performed.&#x20;

However in some cases, it makes more sense to place this on the Triggering element;

* A button might choose to seek to the start of the video.  A different button might seek to 20 sec into that same video&#x20;

SA5 Events has this flexibility inherently.

In our example, this data attribute;&#x20;

```
sa-event-action-video-seek:pos = 80%
```

It can be placed on the Event, alongside the `sa-event-action-video-seek` attribute.&#x20;

Or it can be placed on the Triggering element.&#x20;







