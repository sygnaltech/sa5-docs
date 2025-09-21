# Video Actions 🧪

## Goals&#x20;

* Work with all video types
  * HTML Embed `<video>` element&#x20;
  * Webflow Video element ( aka. Embedly )&#x20;
  * Webflow YouTube element&#x20;
  * Webflow Background Video element&#x20;
  * HTML Embed Vidzflow video&#x20;
* Auto-Detect the Video type&#x20;
* Support Wrapper-based attributes so that the video type can be changed later with no change to the SA5 Events implementation&#x20;





Wistia?&#x20;



Mobile tests-

```
<iframe src="your-video-url" playsinline></iframe>

```



Technical Notes

User Interaction Requirements&#x20;

```
let userInteracted = false;

document.addEventListener("click", () => userInteracted = true);
document.addEventListener("keydown", () => userInteracted = true);
document.addEventListener("touchstart", () => userInteracted = true);

// Check later
if (userInteracted) {
    console.log("User has interacted.");
}

```





```
const testVideo = document.createElement("video");
testVideo.muted = true;
testVideo.play().then(() => {
    console.log("Autoplay is allowed. User may have interacted.");
}).catch(() => {
    console.log("Autoplay is blocked. No interaction yet.");
});

```

```
if (navigator.userActivation?.isActive) {
    player.unmute();
    player.play();
} else {
    player.mute();
    player.play();
}

```











Embed.ly&#x20;

[https://www.npmjs.com/package/player.js](https://www.npmjs.com/package/player.js)



Vimeo

[https://github.com/vimeo/player.js](https://github.com/vimeo/player.js)



## Usage Notes&#x20;

### Play Video

#### `sa-action-video-play` = ( event name )&#x20;

Will begin playing the current video when this event is fired.&#x20;





### Pause Video&#x20;

**`sa-action-video-pause` = (&#x20;**_**event name**_**&#x20;)**&#x20;



### Seek Video&#x20;



### `sa-action-video-seek` = ( event name )&#x20;

Seeks the current video when this event is fired.&#x20;



Restart would be Seek 0.&#x20;



Mute Video&#x20;

Unmute Video&#x20;









Pauses the current video when this event is fired.&#x20;



sa-action-video-restart&#x20;

### sa-action-video-seek:pos = ( position to seek )&#x20;

Position to seek&#x20;

Defaults to 0 ( beginning of video )

Can be;

* Numeric - specifies seconds from start e.g. 10&#x20;
* Percentage - e.g. 80%&#x20;

{% hint style="info" %}
Can be placed on the action element, directly on the the video, OR it can be placed&#x20;
{% endhint %}



sa-action-video-toggle&#x20;





sa-action-video-mute&#x20;

sa-action-video-unmute&#x20;



## Technical Notes&#x20;

Wrapped video element

Convenient for swapping out video type later&#x20;

HTML embedded

```
div.w-embed 
video 
```

Custom element

```
video  
```

div.w-embed-youtubevideo&#x20;



YouTube Video

```
div.w-embed-youtubevideo 
> iframe 
```







General Video

```
div.w-video.w-embed 
> iframe.embedly-embed 
```



Background Video&#x20;

```
div.w-background-video.w-background-video-atom 
> video   = 
```

Vidzflow &#x20;

```
div[data-video-id] 
iframe[src https://app.vidzflow.com/ ] 
```





## Future&#x20;





Autoplay

Muted

Loop

Click to play

Start playing when in view&#x20;

Play inline&#x20;

Overlay&#x20;

Used as a background video&#x20;

Play from start when fullscreen&#x20;



CTA&#x20;























