---
description: Use Google Sheets as a Datasource in Webflow
---

# Google Sheets Data Source ⛔

{% hint style="danger" %}
**CURRENTLY SA4 ONLY**\
This datasource will be completely redesigned for SA5.
{% endhint %}

Sygnal Attributes can use a public Google Sheet as a datasource. It retrieves the Google Sheet data as CSV and converts it to JSON for easy use.&#x20;

### EXAMPLE - Google Sheet to JSON <a href="#demo---google-sheet-to-json" id="demo---google-sheet-to-json"></a>

_Requires a Google Sheet ID which is configured for public read access._

```json
[
  {
    "Rank": "1",
    "Country": "China",
    "Region": "Asia",
    "Population": "1,411,778,724",
    "Percent": "17.90%"
  },
  {
    "Rank": "2",
    "Country": "India",
    "Region": "Asia",
    "Population": "1,381,914,537",
    "Percent": "17.50%"
  },
  {
    "Rank": "3",
    "Country": "United States",
    "Region": "Americas",
    "Population": "332,367,628",
    "Percent": "4.21%"
  },
  {
    "Rank": "4",
    "Country": "Indonesia",
    "Region": "Asia",
    "Population": "271,350,000",
    "Percent": "3.44%"  
  }
]
```

[Open Google Sheet](https://docs.google.com/spreadsheets/d/16lPOiFz5Ow-FTro5SWS-m00fNhRjgsiyeSBdme3gKX0/edit#gid=0)

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Make certain that the Google Sheet is publicly accessible for read-only viewing. This is what the sharing settings will look like.

![Google document sharing](https://wfu.sygnal.com/docs/datasources/google-sheet-data/images/sharing.png)

## Code example

This is a simple example of retrieving the content of a Google Sheet, and then displaying it as an HTML table.&#x20;

{% code overflow="wrap" %}
```html
<script type="module"> 
import { getGoogleSheetData } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/datasources/google-sheet-data.min.js'; 
import { displayDataAsHtml } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/modules/webflow-html.min.js'; 
$(function () { 
  // Get data 
  const sheetId = '16lPOiFz5Ow-FTro5SWS-m00fNhRjgsiyeSBdme3gKX0';
  getGoogleSheetData(sheetId)
    .then((res) => { 
      displayDataAsHtml( $("#json1"), res );
    }, (err) => { 
      console.log(err); 
    }); 
}); 
</script> 
```
{% endcode %}



\
