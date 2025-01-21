---
description: Styling your Markdown content with themes
---

# Themes

Markdown can be themed by specifying a theme attribute, e.g.;

```
<markdown theme="theme1">
 ...
</markdown>
```

When unspecified, this will default to a theme named `default`.&#x20;

This attribute allows you to target CSS directly on the markdown.

The default theme includes some basic table styling and nothing more.&#x20;

### Custom Themes

When a markdown element is converted to markdown it is wrapped in a DIV with an attribute of theme=theme-name, according to your specified theme or `default`.  &#x20;

This can be used in CSS for example;&#x20;

```scss
[theme=default] table {
    border-spacing: 10px 10px; 
    margin-bottom: 1rem; 
}
```





