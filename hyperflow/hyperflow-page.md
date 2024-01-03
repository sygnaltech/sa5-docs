# Hyperflow Page

Hyperflow Page is a core architecture piece which fields the responses for every content page on the actual site.

It handles a wide range of permutations, such as;

* Remove conditionally visible elements
* Remove gated content by User Accounts access group
* Modify links to page-default settings such as `rel=nofollow` or `target=_blank`

## Config

```
// Some code
<script type="application/sa5-config">
[
    { "sitemap": { "lastUpdated": "2023-11-06" } },
    { "conditional": "remove" },
    { "nofollow": "external" }
]
</script>
```
