---
description: Define what events you want triggered in advance
---

# Video Playback Spec 🧪

## Named events

Goals, easier code.

Less code interaction.

Better integration with existing specs, like chapters.&#x20;



Chapters

Youtube&#x20;

1. **Timestamps in Description**: Chapters are created using timestamps listed in the video's description.
2. **Starting Point**: The first timestamp must start at `0:00`, and the chapter title should typically be "Intro" or any other suitable title the creator wants to use.
3. **Format**: Timestamps are written in the `MM:SS` format for videos under an hour, and `HH:MM:SS` for videos over an hour. After the timestamp, the creator provides a space, followed by the chapter name.
4. **Minimum Duration**: For a video to have chapters, it must have at least three timestamps listed, and each chapter must be at least 10 seconds long.

```
// Some code
0:00 Intro
1:23 Part 1: Basics
3:45 Part 2: Advanced Topics

```

{% embed url="https://www.googleapis.com/youtube/v3/videos?part=snippet&id=YOUR_VIDEO_ID&key=YOUR_API_KEY" %}

{ "snippet": { ... "description": "0:00 Intro\n1:23 Part 1: Basics\n3:45 Part 2: Advanced Topics" ... } }



Some events are automatic

stop

play

pause

buffer

seek



This is primarily for special, named events that relate to certain parts of your video.

Import Youtube's standard?



```html
// Some code 
<script type="sygnal/sa5-video">
show-button: 15.28s
navigate: 98%
pause: pause
</script>
```



Use the [`videos.list`](https://developers.google.com/youtube/v3/docs/videos/list) method with the `snippet` part.

```
// Some code
const description = "0:00 Intro\n1:23 Part 1: Basics\n3:45 Part 2: Advanced Topics"; // This would come from the API.
const regex = /(\d{1,2}:\d{2}(?:\:\d{2})?)\s(.+)/g;
let match;
const chapters = [];

while (match = regex.exec(description)) {
    chapters.push({
        timestamp: match[1],
        title: match[2]
    });
}

console.log(chapters);

```





## Chapters

Also supported by;&#x20;

1. **YouTube**
2. **Loom**
3. **Apple Podcasts & iTunes**: Chapters can be added to podcasts, which allows listeners to skip to specific segments of the episode.
4. **Overcast**: A popular podcast player that supports chapters.
5. **Podcast Chapters**: A macOS app specifically designed to add chapters to podcasts.
6. **MKVToolNix**: It's a tool for Matroska (MKV) files, and one of its features is to create or edit chapters.
7. **Auphonic**: An online audio and podcast processing tool that supports chapter markers.
8. **Podlove Web Player**: A web-based podcast player that supports chapters.
9. **Simple Chapters**: An open standard for adding chapter information to MP4s and MP3s.
10. **M4A files**: The M4A file format, primarily used by Apple for songs without DRM protection in iTunes, supports chapters.
11. **Audible**: The audiobook platform uses chapter functionality, allowing listeners to navigate between different sections of the book.&#x20;

## JSON Approach

Too verbose, dislike.

```html
<script type="sygnal/sa5-video">
{
    "events": [
        {
            "type": "time",
            "value": 15.28,
            "action": "show-button"
        },
        {
            "type": "percentage",
            "value": 98,
            "action": "navigate"
        },
        {
            "type": "state",
            "value": "pause",
            "action": "pause"
        }
    ]
}
</script>

```







