# Macro Expansion

WFU macro expansion allows you to populate specific values in your Webflow pages, from a remote data source.

Insert text strings, numeric values, or calculated spreadsheet results anywhere you like.

Values are stored in a dictionary-style JSON array.

## Preparing the Dictionary <a href="#preparing-the-dictionary" id="preparing-the-dictionary"></a>

1. Load data from an external data source. Here we’re using a [Google Sheet](https://docs.google.com/spreadsheets/d/16lPOiFz5Ow-FTro5SWS-m00fNhRjgsiyeSBdme3gKX0/edit#gid=118669749) with calculated fields.
2. The data source must have 2 identified columns - a unique Key column, and Value column. In a Google Sheet source, those are unique column header names. In this demo we are using `Name` and `Value`.
3. Construct a dictionary structure with those key-value pairs. This is a javascript `Map` element.
4. Find all HTML elements tagged to a specific Key, and load that Value.

### Example JSON content <a href="#example-json-content" id="example-json-content"></a>

This is the Google Sheet content, after it has been converted to JSON. Note the `Key` and `Value` column names become field keys in the JSON.

```
[
  {
    "Name": "Countries",
    "Value": "241"
  },
  {
    "Name": "Europe",
    "Value": "52"
  },
  {
    "Name": "Population",
    "Value": "7,780,381,869"
  },
  {
    "Name": "SizeBillion",
    "Value": "2"
  },
  {
    "Name": "Size100Million",
    "Value": "14"
  }
]
```

Once the dictionary is created, you can use it.

## Applying the Dictionary <a href="#applying-the-dictionary" id="applying-the-dictionary"></a>

#### Option 1: Tagged Elements <a href="#option-1-tagged-elements" id="option-1-tagged-elements"></a>

Identify elements in which you want data loaded where, using the `wfu-map-dict` custom attribute.

e.g. `<span wfu-map-dict="Countries"></span>`

Each of the bolded values in this list are loaded dynamically from the Google Sheet.

* Countries: 241
* Europe: 52
* Population: 7,780,381,869
* Size > 1 Billion: 2
* Size > 100 Million: 14

#### Option 2: Macro Expansion <a href="#option-2-macro-expansion" id="option-2-macro-expansion"></a>

WFU also provides for macro expansion. In your text, use the construction `{{ Key Name }}` to identify where you want values inserted. This is particularly of use in Rich Text Elements.

Text or Rich Text element itself must be tagged with the custom attribute `wfu-data-macros="datasourceName"`.

```
Global population is growing!
                    
Currently, there are {{ Countries }} countries in the world,
of which {{ Europe }} are in Europe.
                    
Of a total global population of {{ Population }},
{{ Size100Million }} of our contries are over 100 million population,
with {{ SizeBillion }} over 1 billion.
```

Here’s an example of tag-expanded content.

Global population is growing!

Currently, there are 241 countries in the world, of which 52 are in Europe.

Of a total global population of 7,780,381,869, 14 of our countries are over 100 million population, with 2 over 1 billion.

\
