# Conversion Tracking Event

Goals;

* Easily identify and define a conversion event
  * Page visits, e.g. /success page
  * Form submissions
    * Via Basin&#x20;
* Capture all relevant source data&#x20;
  * Referer
  * UTMs
  * etc.&#x20;
* Capture relevant conversion data
  * Transaction ID
    * From querystring, etc.&#x20;
  * Conversion type
  * Conversion item
* Clean data
  * Via transaction ID&#x20;
  * SPAM-free, e.g. Basin&#x20;
* Configure it for;
  * Custom logging URL&#x20;

## Conversion Event Config

Conversion events are configured in an [SA5 Configuration Block](../overview/configuration-blocks.md)&#x20;





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



## Placement&#x20;



These can be placed in a webpate

<img src="../.gitbook/assets/file.excalidraw (1) (1) (1) (1).svg" alt="" class="gitbook-drawing">





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



## Configuration Settings&#x20;

### url

Specifies the conversion event logger URL base, without querystring params

### type & item&#x20;

Describe the type of conversion for data processing purposes, since different conversions

### class ( FUTURE ) &#x20;

* Purchase - payment captured
* Booking - reservation, but no money captured
* Enquiry -&#x20;
* Enrollment - good lifetime value, no immediate purchase&#x20;

### value ( FUTURE )&#x20;

### transactionIdType & transactionId

Indicates the type of the transaction ID&#x20;

| transactionIdType | transactionId                                  | Notes                                                                                                                         |
| ----------------- | ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `query`           | querystring param name                         | Retrieves the transactionId from the querystring via the named param                                                          |
| `auto`            | <p>querystring param name <br>( optional )</p> | <p>Auto-generates a transactionId from crypto.<br>Automatically adds it to the redirect as the given param, if specified.</p> |





## Future

### transactionId

* Push onto redirect URL in Webflow Forms&#x20;
  * Allow ?param to be specified

unknown utm\_source for unknown referers

* First pass in lib
* Fallback to generic hostname tracking&#x20;

configurable param on redirect&#x20;

### Single-send

When a conversion is registered, avoid re-sending the same conversion Id&#x20;

Check in session, etc.&#x20;

ConversionLogged yes&#x20;



