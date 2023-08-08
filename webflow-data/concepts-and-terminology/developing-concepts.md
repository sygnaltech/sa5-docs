---
description: Cool Stuff We're Thinking About
---

# Developing Concepts

## Tables/Records/Columns v. Sets/Objects/Fields

These are similar concepts and in most cases we'd relate this using a mental spreadsheet paradigm as Tables & Rows. However, the Sets and Keys and Objects paradigm seems more in line with some of the data we're working with;

* Objects with depth
* Objects containing arrays

This becomes even more relevant as we add other types of data to the Datastore, which does not follow the CMS's table-like composition.&#x20;

From a naming perspecting

#### Challenges;

Objects can contain arrays. Therefore we need to be able to resolve a DSD to a selector type, i.e. Set ( keyed or unkeyed ), Object, or Field.  or Invalid ( and in what way, for error logging )&#x20;

Table / Set / Class / Collection &#x20;

Record / Object / Tuple / Item&#x20;

Column / Field / ~~Attribute~~&#x20;

Field types



#### Advanced ideas;&#x20;

Stored Procs / Methods&#x20;

PK FK AK Identity&#x20;

Object paradigms; Inheritance, Methods, Base classes, Interfaces&#x20;

Classes ( object definitons )&#x20;

Attributes- use this to refer to META data regarding an item&#x20;

## Object Metadata

This is a feature we've wanted in Webflow's CMS for some time, and we may be able to add some of these features into SA5.

* Image width, height, type, filesize
* Video duration
* Text length and word-count and language&#x20;

## Keyed v. Unkeyed Datasources

{% hint style="info" %}
This distinction is currently under development. At present, only keyed sources are directly supported.&#x20;
{% endhint %}

In a keyed datasource, you can retrieve a specific item by reference. In an unkeyed datasource, you can only perform list-wide operations.

|                                   | Keyed Datasource         | Un-keyed Datasource |
| --------------------------------- | ------------------------ | ------------------- |
| Retrieve a specific object by key | Yes. E.g a CMS item slug | No                  |
| Retrieve object by position       | ?                        | ?                   |
| Count items                       | Yes                      | Yes                 |
| Sort items                        | Yes                      | Yes                 |
| Bind to a list                    | Yes                      | Yes                 |

## Data Shapes <a href="#data-shapes" id="data-shapes"></a>

WFU utilizes primitive structural patterns which we refer to as **data shapes**;

1. **Table.** A JSON array in which each element contains the same set of keys. Typically this is constructed from a tabular source such as a Webflow Collection List, or a CSV file.
2. **List.** A Table with only one or two fields per element. Lists are primarily used for data-binding to FORM controls.
3. **Dictionary.** A List, which has a `key` field and a `value` field. The key field content is expected to be unique. Dictionaries are used for lookups in template processing.
4. Media.

## Advanced DSNs

A DSN typically includes:

* The name of the database driver (for example, PostgreSQL, MySQL, Oracle, etc.)
* The hostname of the database server
* The port number to connect to (if it's not the default port for the database)
* The name of the database to connect to
* The username and password for the database (though for security reasons, it's often best to supply these separately rather than including them in the DSN)

The exact format of a DSN can vary depending on the database driver. Here's an example of what a DSN might look like for a PostgreSQL database:

A DSN is typically used when setting up a database connection in an application. The DSN is given to the database driver or connection library, which parses the string and uses the information to establish a connection to the database.

## Query Languages

SQL, GraphQL, XPath, etc.&#x20;

## Views

Pre-defined named data views that include filtering and sorting constraints

## Transform / Qualifier Suffixes

e.g. ? to indicate missing values = null&#x20;

## Logic

IF-THEN, for-each, loops...

## Formulas

Basic math in the form of evaluations&#x20;

## Caching

Indexes

Views



## Relational Concepts

1. **Tables (Relations)**:
   * These are the primary data structures in an RDBMS.
   * A table consists of rows and columns where each row represents a record and each column represents an attribute or field of the record.
2. **Indexes**:
   * These are data structures that improve the speed of data retrieval operations on a database table.
   * Common types of indexes include B-trees and hash indexes.
   * Indexes can be unique (enforcing the uniqueness of a value in a column) or non-unique.
3. **Views**:
   * A virtual table that represents the result of a stored query. Unlike tables, views don't store data; they display data from one or multiple tables through a specific query.
4. **Stored Procedures**:
   * These are sets of SQL statements that can be stored in the database and executed as a single unit.
   * They can take parameters and return results.
5. **Triggers**:
   * These are automatically executed (or fired) by the RDBMS in response to specific events on a particular table or view. Common events include insert, update, and delete operations.
6. **Cursors**:
   * These are database objects used to traverse the records in a result set one by one and potentially make changes to the records.
7. **Constraints**:
   * These are rules enforced on data columns of a table.
   * Examples include primary keys, foreign keys, unique constraints, and check constraints.
8. **System Catalog**:
   * This is a collection of tables and views that contain metadata about the RDBMS, detailing all other objects in the database, their structure, and various attributes.
9. **Transaction Logs**:
   * These are logs that keep a history of all transactions and changes in the database. They are crucial for ensuring data integrity and for recovery operations.
10. **Data Files**:

* Physical files on disk where the actual data from tables and other objects is stored.

11. **Control Files**:

* These are files that contain metadata about the physical structure of the database, including the database's creation date, the location of data files and redo log files, and the current log sequence number.

\






