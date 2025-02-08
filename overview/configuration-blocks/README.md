# Configuration Blocks

Configuration Blocks have many purposes;

* Attribute library configuration
* Callback handlers&#x20;
* Special functionality, like Trigger or Action definitions &#x20;

## Usage Notes&#x20;

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

{% hint style="success" %}
In the SA5 documentation, configuration blocks will be presented for you to easily copy, paste, and edit in your Webflow project.&#x20;
{% endhint %}

{% hint style="info" %}
Explore the full details of Sygnal's [configuration block specification](configuration-block-specification.md).&#x20;
{% endhint %}

### Configuration Script Attributes&#x20;

The script tag supports has 3 defined attributes;&#x20;

<table><thead><tr><th>Attribute</th><th width="171">Required?</th><th>Value</th><th>Notes</th></tr></thead><tbody><tr><td><code>type</code> </td><td>Required</td><td><code>application/sa+json</code> </td><td></td></tr><tr><td><code>handler</code> </td><td>Required</td><td>The handler's name </td><td>See the module documention for details. </td></tr><tr><td><code>name</code> </td><td>Varies, depending on the handler </td><td>The specific name of the configuration block, which is library-dependent. </td><td></td></tr></tbody></table>

### Configuration Block Metadata&#x20;

{% hint style="info" %}
Currently, SA configuration blocks are always JSON, as identified in the MIME type.  In the future, we'll be expanding to support other formats.&#x20;
{% endhint %}

<table><thead><tr><th>Key</th><th width="283">Value</th><th></th></tr></thead><tbody><tr><td><code>@context</code> </td><td><code>https://attr.sygnal.com</code> </td><td></td></tr><tr><td><code>@version</code> </td><td><code>0.1</code> </td><td>Indicates the version of the configuration block being used. Specific modules may increment this. </td></tr></tbody></table>

### Configuration Block Contents&#x20;

The JSON content used depends on the handler type. &#x20;

See the module documentation for details.&#x20;







