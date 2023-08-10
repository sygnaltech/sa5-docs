---
description: Configure SEO rules on your links, to control link equity
---

# Nofollow ❺🧪

Check-&#x20;

* custom attributes support for rel=
* Rich Text element links support for rel= as custom attributes

Challenges-

* Make certain the library runs immediately without `defer`&#x20;
* Yet, give it configuration&#x20;

## Goals

* Option to automatically set the rel rules for all external links
* Option to automatically set the rel rules for all links at a certain hostnames&#x20;
* Keep links functional even if JS is disabled&#x20;
* Per-link rules? Using... username?

Webflow does not give the ability to set `rel` links especially in CMS-bound content

* rel="nofollow"
* rel="sponsored"
* rel="ugc" ( user-generated content )&#x20;

[https://developers.google.com/search/docs/crawling-indexing/qualify-outbound-links](https://developers.google.com/search/docs/crawling-indexing/qualify-outbound-links)

[https://developers.google.com/search/docs/crawling-indexing/javascript/javascript-seo-basics](https://developers.google.com/search/docs/crawling-indexing/javascript/javascript-seo-basics)





## What is the purpose of `nofollow`?

The `nofollow` attribute in links tells search engines not to follow a link or pass any link equity (often referred to as "link juice") to the linked page. Over the years, the way search engines treat `nofollow` has evolved, and its implications for SEO have become more nuanced. Here are some points to consider about the SEO value and purposes of using `nofollow`:

1. **Control Over Link Equity**: Originally, the main purpose of `nofollow` was to prevent the passing of link equity to other pages. This means if you have a page with high authority and you link to another page with `nofollow`, the linked page won't benefit from your page's authority.
2. **User-generated Content**: Sites with user-generated content, like forums or blog comments, often use `nofollow` to deter spammers from posting links just to gain link equity. By making links `nofollow`, they signal to spammers that posting links won't provide any SEO benefit.
3. **Paid Links**: Google's guidelines state that paid links should be marked as `nofollow` to prevent link-based manipulation of its search results. Sites that don't adhere to this can face penalties.
4. **Crawl Prioritization**: By using `nofollow`, webmasters can give search engine crawlers hints about which pages they might consider less important to crawl. However, note that `nofollow` doesn't guarantee that a page won't be crawled, but it can influence a crawler's behavior.
5. **Evolution of Nofollow**: Google announced in 2019 that it began treating the `nofollow` attribute as a "hint" rather than a directive. This means that while they consider the `nofollow` signal, they might choose to ignore it in some cases when indexing and ranking content.
6. **Additional Link Attributes**: Alongside the change to `nofollow`, Google introduced two additional link attributes: `rel="sponsored"` (to identify paid or sponsored links) and `rel="ugc"` (to identify links within user-generated content). These provide webmasters with more granular tools to indicate the nature of links to search engines.
7. **Internal Nofollow Links**: Using `nofollow` on internal links (links going to another part of the same website) is less common and can be tricky. While there might be specific scenarios where it's beneficial (like linking to login pages or terms & conditions), it's generally advisable to let link equity flow naturally within your site.

In conclusion, while the `nofollow` attribute can be a valuable tool in specific SEO scenarios, its use should be strategic. It's essential to understand when and why to apply it and to stay updated with search engine guidelines and best practices.

