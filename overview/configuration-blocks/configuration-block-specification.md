# Configuration Block Specification

All SA configuration blocks are HTML `<script>`elements with a specific structure.

Here's an example;&#x20;

```html
<script type="application/sa+json" handler="handler-name" name="my-name">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1",
  ... 
}
</script>
```





The script tag supports has 3 defined attributes;

### `type` = `application/sa+json`&#x20;

Identifies the script MIME type as an SA configuration block.&#x20;

{% hint style="success" %}
SA6 will support [Sygnal's HSON data format](https://hson.sygnal.com/) natively as well, with the `application/sa+hson` type.&#x20;
{% endhint %}







* Type
* Name
* Handler



Here's an example;&#x20;

```html
<script type="application/sa+json" handler="handler-name" name="my-name">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1",
  "url": "https://conversion-tracker-url.com", 
  "transactionIdType": "query", 
  "transactionId": "transactionId",
  "type": "contact",
  "item": ""  
}
</script>
```







## Engineer's Technical Notes&#x20;

We've designed SA's Configuration Blocks protocol with a number of primary considerations.&#x20;

Standards compliance;&#x20;

* Conventional HTML `<script>` mechanics are used&#x20;
  * Scripts are never rendered as page content &#x20;
  * The MIME type ensures that it is not confused with regular scripts &#x20;
* Conventional JSON standards are supported&#x20;

Script efficiency;&#x20;

* SA library scripts can easily locate relevant configuration blocks&#x20;
  * Explicit types can be found by matching the handler name; \
    script\[handler="handler-name" i]&#x20;
  * And/or the handler categories; \
    `script[handler="handler-name" i], script[handler^="handler-name." i]`&#x20;
  * Where possible these handler names are case-insensitive&#x20;
* Configuration blocks can also be identified by specific name&#x20;
*

Convenience

* Where possible, case-insensitive value matches \
  `script[handler="handler-name" i]`&#x20;

Extensibility & future proofing; &#x20;



```
'script[handler="foo" i], script[handler^="foo." i]'
```



e.g. a typical Basin Contact Us form&#x20;

```html
<script type="application/sa+json">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ConversionEvent",
  "@version": "0.1",
  "url": "https://conversion-tracker-url.com", 
  "transactionIdType": "query", 
  "transactionId": "transactionId",
  "type": "contact",
  "item": ""  
}
</script>
```

* Data pulled in from session var&#x20;
* Overridden with data here
* TransactionID created / set&#x20;



Make these easier to find&#x20;

```html
<script type="application/sa5+json" handler="ConversionEvent">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ConversionEvent",
  "@version": "0.1",
  "url": "https://conversion-tracker-url.com", 
  "transactionIdType": "query", 
  "transactionId": "transactionId",
  "type": "contact",
  "item": ""  
}
</script>
```











## Decisions&#x20;

`@context`

`@type`



`@version`









```html
<script type="application/sa+json" handler="Trigger.Timer">
{
  "@context": "https://attr.sygnal.com",
  "@type": "TimerTrigger",
  "@version": "0.1",
  "timer": "60", 
  "timerRepeat": "120",
  "event": "my-event" 
}
</script>
```







```html
<script type="application/sa+json" handler="Event" name=""> 
{
  "@context": "https://attr.sygnal.com",
  "@type": "TimerTrigger",
  "@version": "0.1",
  "timer": "60", 
  "timerRepeat": "120",
  "event": "my-event" 
}
</script>
```





? change @type to @handler   &#x20;

? is there value to context and type?  &#x20;

SEO?&#x20;

Docs?&#x20;

Make these easier to find&#x20;

```html
<script type="application/sa5+json" handler="ConversionEvent">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ConversionEvent",
  "@version": "0.1",
  "url": "https://conversion-tracker-url.com", 
  "transactionIdType": "query", 
  "transactionId": "transactionId",
  "type": "contact",
  "item": ""  
}
</script>
```











### Named Config Blocks

Used when referenced from a `:config` modifier on a base attribute.&#x20;

```html
<script type="application/sa5+json" name="foo">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ConversionEvent",
  "@version": "0.1",
  "url": "https://conversion-tracker-url.com", 
  "transactionIdType": "query", 
  "transactionId": "transactionId",
  "type": "contact",
  "item": ""  
}
</script>
```

* `name` added&#x20;





## Supported Data Formats

* JSON
* HSON ( coming soon )&#x20;

## Approach Notes

We're moving towards a precedent set by JSON-LD, as it's cleaner and more utilitarian.&#x20;

### About the MIME Type

In general, we'll stick with standard conventions; &#x20;



The type of application/sa+json follows conventions like JSON-LD, which is \`application&#x20;





```
application/sa+json
```

```
application/sa+hson
```





## Legacy&#x20;

```
application/sa5+json
```

```
application/sa5+hson
```



* **`application/`**:
  * The primary type (`application`) represents a **general type of data**. It’s often used for data that doesn't fall under other primary types such as `text`, `image`, `audio`, etc.
  * `application/` typically indicates that the content **is not intended to be directly displayed** to the user but rather used or processed by an application. For example, `application/json`, `application/xml`, and `application/pdf` indicate that the content is primarily intended for programmatic use.
* **`sa5+json`**:
  * The `+json` suffix tells the system that the content is in **JSON format** and should be handled as such. It helps parsers and applications recognize how to process the content.
  * The `sa5` is a custom subtype, giving a specific indication about what the JSON content represents in the context of your system.

####

