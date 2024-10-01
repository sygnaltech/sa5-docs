# Video Player ( Direct )

## Webflow's Limitations

Webflow uses Embed.ly for its video handling.&#x20;

Embed.ly does not support direct video links, which means that all video on Webflow MUST be served through a provider such as Vimeo or YouTube.&#x20;

[https://embed.ly/providers](https://embed.ly/providers)

## Need&#x20;

A user has a video that they want to add to;&#x20;

* A site element
* Within a blog post
* To a CMS item, as a video or within a lightboxed image gallery&#x20;

Webflow has a video element, a CMS video field, and a lightbox



|                             | Webflow                                                       | SA5                                                                                                            |
| --------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Video element               | Supported, Embed.ly compatable sources only                   |                                                                                                                |
| Video lightbox              | Supported, Embed.ly compatable sources only                   |                                                                                                                |
| Video lightbox in Rich Text | -                                                             | <ul><li>Embed an image, link it directly to an MP4</li><li>SA5 sees this and handles the lightboxing</li></ul> |
| Video element in Rich Text  | <p>Embed.ly-only.  <br>Still has a bug with API-setting? </p> |                                                                                                                |
| CMS Video field             | Can be bound to an element                                    |                                                                                                                |
| Background video            | Upload, compress, use                                         | ? Replace this with an external source                                                                         |

All of Webflow's sources support Embed.ly compatable sources.&#x20;













