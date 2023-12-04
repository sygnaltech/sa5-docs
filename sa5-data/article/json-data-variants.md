---
description: A review of JSON data variants and how they relate to SA5
---

# JSON Data Variants

JSON is great, but it has a few key limitations;

Pros;

* Plain-text, easy to type
* 100% JS-compatible. This is what JSON is for, "JavaScript Object Notation."

Cons;

* Its syntax is strict, and easy for a non-dev to mess up&#x20;
* It is not very strongly typed&#x20;
* It's not directly compatible with Webflow's custom code features, which always HTML encode embedded CMS vars.&#x20;

SA5 Data & the Introduction of HSON

## HSON ( HTML Structured Object Notation )

HSON is a format designed by Sygnal, specifically to close a few key gaps in&#x20;

It borrows design concepts from JSON and YAML, but has key distinctions;

* Possesses a simpler syntax for structure and key-value notation, akin to YAML
* The **values** in HSON are always HTML-encoded, in line with Webflow's field-embed design
* It adds some strong-typing capabilities to allow for more intelligent structure creation&#x20;

{% hint style="info" %}
Add dates. Support intrinsic Webflow date format if possible.&#x20;
{% endhint %}

SA5 Data, aka. HSON was designed by Sygnal specifically for Webflow.&#x20;

Alt names considered: Sygnal Structured Object Notation (SSON), Webflow Structured Object Notation (WFSON), HTML Structured Object Notation (HTMLSON), SA5 Structured Object Notation (SA5SON).&#x20;

## Plain-Text Data Format Notes

### JSON Variants

1. **JSONP (JSON with Padding)**: Primarily used to overcome the cross-domain policies in web browsers, JSONP includes a JSON payload wrapped in a function call. It's used in JSON data requests from a different domain than the one the script originated from.
2. **NDJSON (Newline Delimited JSON)**: A stream-friendly format where each line is a valid JSON object. Useful for processing large JSON files or streams of data without needing to parse the entire dataset at once.
3. **JSON-LD (JSON for Linked Data)**: A method of encoding Linked Data using JSON. It is used to serialize Linked Data and connect it to web-based, structured data.
4. **GeoJSON**: A format for encoding a variety of geographic data structures using JSON. It's used for representing simple geographical features, along with their non-spatial attributes.
5. **JSON5**: An extension to JSON that aims to make JSON code easier for humans to write and read, incorporating features from ECMAScript 5.
6. ~~**JSONC**: A compressed form of JSON that aims to reduce the size of the JSON data.~~
7. ~~**BSON (Binary JSON)**: A binary-encoded serialization of JSON-like documents. Used mainly in MongoDB, it is designed to be efficient in space, but not necessarily in speed.~~
8. ~~**MsgPack (MessagePack)**: It's a binary format that is more efficient than JSON but has JSON-like types. Used for communication between different languages like JSON but in a more compact way.~~

Also look into;

1. **CJSON (Canonical JSON)**: A subset of JSON that is intended to provide canonical encoding of data structures, meaning that data structures encoded in CJSON can be uniquely reconstructed from the byte stream.
2. **JSONT (JSON Template)**: A template engine that uses JSON as its language.
3. **FSON (Function JSON)**: An extension of JSON to support encoding of functions.
4. **JPath**: A query language for JSON, similar in concept to XPath for XML.

Other popular plaintext formats

1. **XML (eXtensible Markup Language)**: A widely used format that is more verbose than JSON. It's suitable for complex data structures and supports namespaces, attributes, and comments. It's commonly used in web services (like SOAP), configuration files, and document formats (like Office Open XML).
2. **YAML (YAML Ain't Markup Language)**: Known for its readability, YAML is often used in configuration files and data serialization. It supports complex data structures, including lists and associative arrays. It's widely used in applications like Docker, Kubernetes, and Ansible.
3. **TOML (Tom's Obvious, Minimal Language)**: Designed to be easy to read and write due to its clear semantics. TOML is used in configuration files and is the default configuration format for Rust's package manager, Cargo.
4. **CSV (Comma-Separated Values)**: A simple format used to store tabular data. Each line is a data record, and each record consists of fields separated by commas. It's widely supported by spreadsheet programs and databases.
5. **INI**: A simple format used for configuration files. It's organized into sections, and each section contains keys with values. The format is straightforward and is used in many applications for storing settings.
6. ~~**Protocol Buffers (Protobuf)**: Developed by Google, this is a binary serialization format that is more efficient and faster than JSON. It's used for storing and exchanging structured data between services.~~
7. ~~**Cap’n Proto**: Similar to Protobuf, but faster as it doesn't require a separate unpacking step. It's designed for high-performance scenarios.~~
8. ~~**MsgPack (MessagePack)**: A binary format that is more efficient than JSON but has JSON-like types. It's used for communication between different languages like JSON but in a more compact way.~~
9. **EDN (Extensible Data Notation)**: A subset of Clojure's syntax designed for extensible data notation. It's similar to JSON but supports more types and is extensible.
10. **S-expressions**: Used primarily in Lisp programming environments, S-expressions are a notation for nested lists of data. They can be used for data serialization in a manner similar to JSON or XML.



Binary Variants

