# Google Sheets

WFU can use public Google Sheets as a data source.

### DEMO - Google Sheet to JSON <a href="#demo---google-sheet-to-json" id="demo---google-sheet-to-json"></a>

Retrieve data from a Google sheet, and convert it to JSON.

_Requires a Google Sheet ID which is configured for public read access._

Demonstration

```
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

\
