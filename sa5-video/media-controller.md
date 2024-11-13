# Media Controller

Early ideas on a universal SA4 controller pattern for media elements.

Media being characterized by;

* Time-based delivery
* Playback speed





which are defined as;

## Use Cases







* video
  * direct MP4
  * youtube
  * bunny.net
  * vimeo&#x20;
* audio&#x20;
  * podcasts
* animation
  * lottie
  * RIVE&#x20;







## CONCEPTUAL

Media element has a name, and "tracks", e.g. typically at least one of;

* video
* audio

### Element-wide Commands

* Play all tracks
* Seek all tracks
  * Absolute
    * Seconds from start
      * ? Seconds from end
    * Frame
    * %
  * Relative
    * \+/- seconds from current position
    * \+/- frames from current position
* Pause all tracks

Possibly;

* Visual-all-track events; fade, etc.&#x20;
* Audio-all-track events; mute, fade, etc.&#x20;

### Audio Track Commands

* Fade out
* Fade in&#x20;
* Apply filters

### Video Track Commands

* Fade to color
* Fade from color
* Apply filters

### Advanced

Playback speed

Scrub in reverse



















