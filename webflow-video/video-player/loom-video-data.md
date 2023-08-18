---
description: Extraction of Loom Data
---

# Loom Video Data 🧪

{% hint style="info" %}
This is not yet an SA5 feature. Notes for consideration.
{% endhint %}

## Video Data

* Thumbnail
* Alt versions
* Chapters
* Stats ( likes, etc )&#x20;
* Metadata markup such as links & end-frames
* Transcription / SRTs&#x20;

Sources to consider;&#x20;

1. **YouTube Data API v3**
2. **Embedded Player Parameters**:
   * When you embed a YouTube video, certain parameters can be added to the URL to control its behavior. While these don't give you new information, they do let you configure how the video is displayed or played.
3. **Public RSS Feeds**:
   * YouTube used to provide RSS feeds for channels which you could use to get a list of videos along with some basic details. However, this method became less accessible over time, and while there are still ways to access RSS data for YouTube, it's less direct and less rich in terms of details compared to the past.
4. **Open Graph Tags & Metadata**:
   * YouTube videos have Open Graph tags and other meta tags to provide data to be used when the video is shared on social platforms. By inspecting the page source or using tools to extract Open Graph data, you can obtain:
     * Video title
     * Thumbnail image
     * Description (though often truncated or limited)
5. **oEmbed Endpoint**:
   * YouTube provides an oEmbed endpoint which returns embed information for a video. You can use it like this: `https://www.youtube.com/oembed?url=http://www.youtube.com/watch?v=[VIDEO_ID]&format=json`
   * This will return some basic data about the video, including title, author\_name, height, width, thumbnail, etc. in JSON format.









