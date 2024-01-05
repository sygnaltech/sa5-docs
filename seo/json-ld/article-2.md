---
description: Generate valid JSON-LD Structured data from CMS Content
---

# JSON-LD Course Info ❺🧪

{% hint style="danger" %}
**EXPERIMENTAL ALPHA** ⑤

DO NOT USE this in production code, as it may be removed. We'll see if this approach works. Testing with Google is in progress.&#x20;

**STATUS**

Testing Google response to our script generated JSON-LD.&#x20;
{% endhint %}

## &#x20;<a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

* [Course list](https://developers.google.com/search/docs/appearance/structured-data/course#guidelines): A rich result that lists courses from the same website.
* [Course info](https://developers.google.com/search/docs/appearance/structured-data/course-info): A carousel that shows detailed course information from a variety of websites.

[https://developers.google.com/search/docs/appearance/structured-data/course#guidelines](https://developers.google.com/search/docs/appearance/structured-data/course#guidelines)

### When to Use

Google actually has some fairly strict and easy requirements if you want to use this type of markup:

* only use it for educational content that fits the criteria for a course i.e. lectures, lessons, or modules in a particular subject
* the course must have ” an explicit educational outcome of knowledge and/or skill in a particular subject and/or topic, and be led by one or more instructors with a roster of students.”
* e.g. a general event such as “how to make eggs” is not a course

[https://jsonld.com/json-ld-course/](https://jsonld.com/json-ld-course/)

## Usage Notes



```html
<script>
var article = new window.sa5.LdJsonCourse();
article.headline = `Article headline`;
article.addAuthor (`Bob Hershel`);
article.publisher = `Sygnal`;
article.generate();
</script>
```



```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Course",
  "name": "Introduction to Computer Science and Programming",
  "description": "Introductory CS course laying out the basics.",
  "provider": {
    "@type": "Organization",
    "name": "University of Technology - Eureka",
    "sameAs": "https://www.example.com"
  }
}
</script>
```

## Notes&#x20;

`hasCourseInstance`

`offers`

Required by Google GSC.&#x20;

[https://search.google.com/search-console/r/course-info?resource\_id=sc-domain%3Asygnal.com](https://search.google.com/search-console/r/course-info?resource\_id=sc-domain%3Asygnal.com)

{% embed url="https://developers.google.com/search/docs/appearance/structured-data/video" %}

## References

[https://developers.google.com/search/docs/appearance/structured-data/course-info](https://developers.google.com/search/docs/appearance/structured-data/course-info)

[https://developers.google.com/search/docs/appearance/structured-data/course](https://developers.google.com/search/docs/appearance/structured-data/course)

[https://jsonld.com/json-ld-course/](https://jsonld.com/json-ld-course/)

[https://schema.org/Course](https://schema.org/Course)
