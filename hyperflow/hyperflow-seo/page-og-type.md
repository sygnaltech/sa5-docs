---
description: Control each page's og:type individually
---

# Page og:type

Webflow automatically inserts this META tag into all pages:

`<meta property="og:type" content="website"/>`

However, there are&#x20;

`<meta property="og:type" content="article"/>`

I tried adding `<meta property="og:type" content="article"/>` to the `<head>` tag of the page settings but now my page has two `<meta property="og:type"` tags in it.

[https://discourse.webflow.com/t/page-is-defaulting-to-meta-property-og-type-content-website/263244](https://discourse.webflow.com/t/page-is-defaulting-to-meta-property-og-type-content-website/263244)

Discussion

\
Yes, there is a significant difference between `<meta property="og:type" content="website"/>` and `<meta property="og:type" content="article"/>`. These are Open Graph (OG) meta tags used to define the type of content that a particular page represents when shared on social media platforms like Facebook, Twitter, and LinkedIn. Here's how they differ:

1. **`<meta property="og:type" content="website"/>`**:
   * This tag is used to indicate that the content being shared is a website.
   * It is typically used for generic pages such as the homepage of a site or a landing page that isn't specifically an article, blog post, or news story.
   * When this tag is used, social media platforms understand that the link being shared is to a website's main page or a general page, and it might not be tied to a specific piece of content or article.
2. **`<meta property="og:type" content="article"/>`**:
   * This tag specifies that the content is an article or a blog post.
   * It is more specific and is used for individual articles or blog posts. This tag tells social media platforms that the link being shared leads to a piece of content that is a standalone article or editorial.
   * This tag can be accompanied by other `og:` tags that provide more specific information about the article, such as `og:title` for the article's title, `og:description` for a summary of the article, and `og:image` for an image associated with the article.

The use of these tags affects how content is displayed and previewed on social media platforms. Choosing the correct `og:type` helps these platforms display your shared content more accurately, with appropriate formatting and information. For example, an `og:type` of `article` might result in the display of the article's author, publish date, or a brief description, while `website` might lead to a more general preview of the web page.

Specifics

Certainly! The way social media platforms handle and display shared links can vary based on the Open Graph (`og`) meta tags used, specifically the `og:type` tag. Let's look at how a link shared on a platform like Facebook might appear differently when using `<meta property="og:type" content="website"/>` versus `<meta property="og:type" content="article"/>`.

#### Example with `<meta property="og:type" content="website"/>`

When you use this tag, it indicates that the link is to a general website or a non-article-specific page, like a homepage. The social media platform's preview might focus on the overall branding of the site.

* **Title**: Usually the name of the website or company.
* **Description**: A general description of the website or its purpose.
* **Image**: Often a logo or main image associated with the website.
* **URL Display**: Typically, the base URL of the website is shown.

**Example Preview for a Website**:

* **Title**: "Tech Gadgets Inc."
* **Description**: "Discover the latest in tech and gadgets. Explore our wide range of products."
* **Image**: Company logo or a featured homepage image.
* **URL**: `https://www.techgadgetsinc.com`

#### Example with `<meta property="og:type" content="article"/>`

This tag is used for specific content pages, like news articles or blog posts. The social media preview is more focused on the content of the individual article.

* **Title**: The title of the article or blog post.
* **Description**: A summary or excerpt from the article.
* **Image**: An image relevant to the article, such as a featured image.
* **URL Display**: The specific URL of the article.
* **Additional Metadata**: May include the article's publication date, author's name, etc.

**Example Preview for an Article**:

* **Title**: "The Future of Smartphones: Trends to Watch"
* **Description**: "In this article, we explore upcoming trends in smartphone technology that are set to transform the industry."
* **Image**: An image from the article, perhaps showing futuristic smartphones.
* **URL**: `https://www.techgadgetsinc.com/blog/future-smartphones`
* **Additional Info**: "Published on January 1, 2023 by John Doe"

In summary, `og:type="website"` typically results in a general preview focusing on the site as a whole, suitable for homepages or corporate pages. In contrast, `og:type="article"` generates a content-focused preview, ideal for individual articles or blog posts, highlighting specific details about that content.

og:types

\
Open Graph (OG) provides several types that can be used in the `og:type` meta tag to define the nature of your content. These types help social media platforms and other services understand what kind of content is being shared, allowing for more accurate and appropriate presentation. Here are some of the common `og:type` values:

1. **website**: A standard website or webpage.
2. **article**: An article or blog post. Often accompanied by additional tags like `og:article:author`, `og:article:publication_time`, etc.
3. **book**: Represents a book. Can include additional properties like `og:book:author`, `og:book:isbn`, etc.
4. **profile**: A personal profile page. It can have properties like `og:profile:first_name`, `og:profile:last_name`, etc.
5. **music.song**: A song. This can include additional properties like `music:duration`, `music:album`, `music:musician`, etc.
6. **music.album**: An album. Accompanied by properties like `music:song`, `music:song:disc`, `music:song:track`, etc.
7. **music.playlist**: A playlist. Can include properties such as `music:song`, `music:song:track`, etc.
8. **music.radio\_station**: A radio station.
9. **video.movie**: A movie. It can include additional properties like `video:actor`, `video:director`, `video:duration`, etc.
10. **video.episode**: An episode of a TV show. Accompanied by properties like `video:actor`, `video:director`, `video:duration`, `video:series`, etc.
11. **video.tv\_show**: A TV show. It can also have similar properties to `video.episode`.
12. **video.other**: Any other type of video content.

Each of these types can be enhanced with additional properties specific to their category, offering a rich and detailed description of the content when shared on social media platforms. This not only improves user engagement but also helps in better content categorization and search engine optimization.

## Config

Approaches;

* Map, based on source paths, e.g. `/blog/*` -> og:type = article
* Individual
  * Pre-facing og:type:override, set at the page level
* Cleanup approach. Remove default, if another is specified, to ensure only one&#x20;

Source page









