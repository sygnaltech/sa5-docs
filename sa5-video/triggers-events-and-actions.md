# Triggers, Events & Actions



## Triggers&#x20;

Not yet implement, considering;

sa-trigger-video-play&#x20;

sa-trigger-video-pause&#x20;

sa-trigger-video-seek&#x20;

sa-trigger-video-position&#x20;

sa-trigger-video-position:pos&#x20;

## Actions

### sa-action-video-play = ( _event name_ )&#x20;

Play the video.

### sa-action-video-pause = ( _event name_ )&#x20;

Pause the video.&#x20;

### sa-action-video-seek = ( _event name_ )&#x20;

Seek the video, to a specified position.&#x20;

#### sa-action-video-seek:pos = ( _position_ )&#x20;

* Unsigned integers indicates a position in seconds, from the start of the video&#x20;
* `+` Integers indicate a number seconds to advance&#x20;
* `-` Integers indicate a number seconds to rewind&#x20;
* Unsigned percentages indicate a position in % of total playtime, from the start of the video&#x20;
* `+` Percentages indicate a % of the total playtime to advance&#x20;
* `-` Percentages indicate a % of the total playtime to rewind&#x20;

{% hint style="info" %}
This attribute can be placed either on the video element, or on the triggering element. &#x20;

* Place it on the video element if the seek position will always be the same when you invoke this Action.&#x20;
* Place it on the triggering element if the seek position can vary depending on the Trigger.&#x20;
{% endhint %}

Examples;&#x20;

<table><thead><tr><th width="140.33331298828125">Seek value</th><th>Behavior</th><th>Notes</th></tr></thead><tbody><tr><td><code>10</code> </td><td>Seek to 10 seconds from the beginning of the video</td><td>If the position given is > the video duration, will seek to end</td></tr><tr><td><code>+10</code> </td><td>Seek +10 seconds</td><td>Will stop if the end of the video is hit</td></tr><tr><td><code>-20</code> </td><td>Seek -20 seconds</td><td>Will stop if the start of the video is hit</td></tr><tr><td><code>10%</code> </td><td>Seek to 10% from the beginning of the video</td><td>If the position given is > the video duration, will seek to end</td></tr><tr><td><code>+20%</code> </td><td>Seek forward 20% of the video duration </td><td>Will stop if the end of the video is hit</td></tr><tr><td><code>-50%</code> </td><td>Seek back 50%</td><td>If the position given is > the video duration, will seek to end</td></tr></tbody></table>









[https://www.npmjs.com/package/player.js](https://www.npmjs.com/package/player.js)
