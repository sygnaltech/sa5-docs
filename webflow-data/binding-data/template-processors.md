---
description: The Details of SA5's Data-binding Template Processors
---

# Template Processors



{% hint style="info" %}
It's generally not advised to mix template processing `{{ ... }}` with element-level processing. Tagging elements with `[wfu-bind]` _within_ `[wfu-bind-content]`-tagged elements _should_ work, but is not well-tested.&#x20;
{% endhint %}



Page lifecycle

Inital load solution

Future&#x20;





### Default SA5 Template Handler

\[wfu-bind-content] with no attribute.



Or `default`.

v1

v2





<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>



Straight literal text

e.g. a

`?code=ID6079&name=Trial+User+1&color=blue&accept=true`

`{{ ?accept }}`



Returns `true`. &#x20;















\{{ straight \}}&#x20;



?&#x20;

## Others Under Consideration



1. **Mustache.js**: This is a logic-less template syntax. It can be used for HTML, config files, source code - anything. It works by expanding tags in a template using values provided in a hash or object. Handlebars.js is actually an extension of Mustache.js and adds additional features on top of it.
2. **EJS (Embedded JavaScript)**: EJS is a simple templating language that lets you generate HTML markup with plain JavaScript. It supports fast rendering, custom delimiters, includes, and both client-side and server-side rendering.
3. **Pug (formerly Jade)**: Pug is a high-performance template engine heavily influenced by Haml and implemented with JavaScript for Node.js and browsers. It offers features like includes, mixins, inheritance, and interpolation, and it compiles directly to JavaScript.
4. **Nunjucks**: Developed by Mozilla, Nunjucks is inspired by jinja2 and supports both block-based and inheritance-based templating. It is simple and extensible and has robust features like autoescaping and macros.
5. **lodash templates**: lodash, a popular JavaScript utility library, provides a simple templating function. It's less powerful than some of the other options on this list, but it's good for simple use cases and you may already be using lodash in your project.
6. **React.js**: React isn't exactly a templating engine—it's a library for building user interfaces. However, it does include a powerful system for building HTML views with JavaScript, using a syntax extension called JSX. If you're already using React, you might not need a separate templating engine.

## Unsupported Template Handlers

### Handlebars.js

{% embed url="https://handlebarsjs.com/installation/" %}

\{{#each people\}} \{{print\_person\}} \{{/each\}}&#x20;

\{{#each persons\}} \{{>person person=.\}} \{{/each\}}



