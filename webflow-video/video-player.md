---
description: Control and get events from your Webflow video players and embeds.
---

# Video Player ❺

{% hint style="info" %}
Currently only supports Vimeo HTML Embeds, as a test.&#x20;
{% endhint %}

## Use Cases

* Perform actions as the player state changes state between stopped, paused, and playing.
* Perform actions as the playback happens, at different times in the video, either by second, or by % complete.&#x20;
* Perform a specific action such as enabling a button when the video reaches a certain point of playback.

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

{% hint style="info" %}
Currently only supports Vimeo HTML Embeds, as a test.&#x20;
{% endhint %}

This initial release is focused on player state change eventing.

### `wfu-video` attribute

Add the `wfu-video` attribute directly to the IFRAME element of the Vimeo embed that you want to watch. Assign it a unique name for that video element, e.g. `my-video`.

### Add the callback ( below )

You will receive playback events for any of the videos you've tagged, including;

* User hits play, pause, or stop.&#x20;
* Video playing time codes and % complete, which you can use to perform other actions.&#x20;

Identify which video is state-changed using the name.

### Video State Changes

When a video state change occurs, it passes two pieces of information into your callback- the name you've assigned to the video and a **player state** information object.

The player state object includes this information;

* `stateChange` - indicates what has changed
  * `timeupdate` indicates the player time has updated, which typically occurs while it is playing.&#x20;
* `at` - indicates the current playback position, in seconds, e.g. 60.088
* `duration` - indicates the total duration of the video, in seconds, e.g. 62,293
* `progress` - indicates the percentage complete of watching the video

Use these in you callback to make decisions and perform actions.&#x20;

## Future

* Support Webflow Video element, YouTube element, and other embeds. Wistia, YouTube, etc.&#x20;
* Prevent skip-ahead?
* Support e.g. auto-pause on scroll off-screen, or on hidden.&#x20;
* ~~Consolidate all eventing to a single player-status updated event.~~ 5.2.30
  * Choose which event types you wish to be notified of.&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this feature, so we’ll use a _no-code_ integration approach.

Install JS in **HEAD**, generally site-wide.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Video -->
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@v5.2.30/dist/nocode/webflow-video.js"></script>
```
{% endcode %}

### STEP 2 - Apply `wfu-video` to the Videos you want <a href="#step-2---apply-wfu-data-poster-url-to-the-background-videos" id="step-2---apply-wfu-data-poster-url-to-the-background-videos"></a>

See above for details.

### STEP 3 - Callbacks

**OPTIONAL.** If you want to receive player state-change information-&#x20;

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['playerStateChange', 
  (name, state) => {
    
//    console.log("STATE CHANGED", name, state, state.stateChange, state.status, state.at, state.duration, state.progress); 

    if(state.progress > 50) // 50% complete 
      enableButton(); // Perform some action 
    
  }]); 
</script>
```

\
