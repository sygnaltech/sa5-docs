# Core Processing





## Eventing&#x20;

Blocking / non-blocking ??&#x20;

* SA5 load starting
  * SA5 lib load starting
    * Custom lib events&#x20;
    * ...&#x20;
  * SA5 lib load finished&#x20;
  * ...&#x20;
* SA5 load finished&#x20;





## Identify All SA Classed Elements



### Includes Config Blocks

Like...

```
<script type="application/sa5+json"> 
{
  "@context": "https://attr.sygnal.com",
  "@type": "ConversionEvent",
  "@version": "0.1",
  "url": "https://sygnal-n8n-u1282.vm.elestio.app/webhook/4eb1125f-ad4f-41d7-8946-a16fe276a8be", 
  "transactionIdType": "auto",
  "type": "contact",
  "item": ""  
}
</script>
```



## Determine Required Modules



## Load Modules Needed&#x20;



## Execute Modules in Order

* Dynamic Attributes&#x20;
  * First, do config blocks
  * Then attributes&#x20;



Layout  &#x20;



| Type    | Module                                                       |                                                                    |                                  |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------------------ | -------------------------------- |
| Event   | SA5 Init Starting                                            |                                                                    |                                  |
| Action  | SA5 Data init                                                | <ul><li>Initialize Data Sources </li></ul>                         |                                  |
| Action  | [Dynamic Attributes](../../sa5-html/sa5-dynamic-attributes/) | <ul><li>First, do config blocks </li><li>Then attributes</li></ul> | Includes start and finish events |
| Action  | SA5 Data binding                                             |                                                                    |                                  |
| Action  | Decode                                                       |                                                                    |                                  |
| Action  | SA5 Layout                                                   |                                                                    |                                  |
|         |                                                              |                                                                    |                                  |
| Action  | SA5 TEA                                                      |                                                                    |                                  |
|         |                                                              |                                                                    |                                  |
| Action  | Unwrap                                                       |                                                                    |                                  |
| Event   | SA5 Init Finished                                            |                                                                    |                                  |









Install CSS

HTML Tools

Remove Elements

Cleanup Conditional Visibility

















