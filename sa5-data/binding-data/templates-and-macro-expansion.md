---
description: The Details of SA5's Data-binding Template Processors
---

# Templates & Macro Expansion 📝

We've redesigned our template processor and data-binding architecture in SA5. These docs will be fully rewritten to cover the new features.&#x20;

{% hint style="info" %}
Until this section is rewritten, refer to the main [Data Binding](./) documentation page.&#x20;
{% endhint %}

## Basic Overview

1. Setup any custom [SA5 Data sources](../article/) you want, from your collection lists.
2. In your text or rich text elements, define a _context_ for your data-binding
3. Tag the elements you are using as templates, which will contain macros, with \[wfu-bind-content]
4. Place macros inside of your text

e.g.;

\{{ $cookie.name \}} would retrieve the value of&#x20;

You can then use SA5's &#x20;





### Dynamic DSD References, using Data-Binding Context

You can specify fixed reference items using a fully-qualified DSD like this, however if the template is in a dynamic context such as a collection list or collection page, SA5 allows you to set the context for partial DSDs to operate in.&#x20;

The way this works is to assign these attributes to the parent of your `wfu-bind-content` tagged element.

* `wfu-bind-dsn` = The data source name, e.g. `my-data`.&#x20;
* `wfu-bind-item-id` = The data source item ID, e.g. `row-28`.&#x20;

{% hint style="info" %}
These context elements can be on the same element as your `wfu-bind-content` tag, but they can also be on any ancestor element. They also do not need to be on the same element. This gives you different flexibilities&#x20;
{% endhint %}



Bind the entire element using wfu-bind, will replace the entire content.&#x20;

In Webflow static ( not CMS-bound ) rich text and plain-text elements you can select text and create a bold, italic, or span sub-element.

When that is created, you can select is separately, and you can assign custom attributes directly to it. In this way you can directly bind parts of a text or rich text element.&#x20;

Another way is macro-expansion \{{ name \}}&#x20;







## SEO Notes

Bound data may or may not be picked up by search indexing bots. Google is generally good at executing script and indexing the page after modification, however you will need to test this yourself. &#x20;





{% hint style="info" %}
It's generally not advised to mix template processing `{{ ... }}` with element-level processing _in the same elements_. Tagging elements with `[wfu-bind]` which are _within_ `[wfu-bind-content]`-tagged elements _should_ work, but is not well-tested.&#x20;
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



