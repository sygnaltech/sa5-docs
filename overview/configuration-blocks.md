# Configuration Blocks



`@context`



`@type`



`@version`





e.g. a typical Basin Contact Us form&#x20;

```html
<script type="application/sa5+json">
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

## Supported Data Format

* JSON
* HSON ( coming soon )&#x20;

## Approach Notes

We're moving towards a precedent set by JSON-LD, as it's cleaner and more utilitarian.&#x20;

### About the MIME Type

In general, we'll stick with standard conventions; &#x20;

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

