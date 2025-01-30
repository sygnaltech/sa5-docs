# Smart Attributes 🧪

{% hint style="info" %}
Feature under consideration.&#x20;
{% endhint %}

## Smart Attributes

On specific element types, certain attributes may be specially identified and the content could be run through additional automatic processing, e.g.

* Boolean types

Checkbox

`x-checked` - when used we'll evaluate the content to SA5 truthy or falsy.&#x20;

* Truthy creates the `checked` attribute
* Falsy does not&#x20;

Select Option;&#x20;

x-value - when used we'll scan the options list

To set a default option in a `<select>` element, you use the `selected` attribute on the desired `<option>` element. Here's how you can do it in HTML:

Note any data-binding SA5 must be done prior&#x20;

## Type Conversion

* Boolean - process as truthy&#x20;
* Numeric -&#x20;
* Defaults, if supplied value is missing or invalid&#x20;
* Suppression, if supplied value is missing or invalid
  * e.g. an invalid `src` was supplied for a video&#x20;

Considering;

* Predefined enumerated value sets, such as input type&#x20;

## Element Types

All Elements

XTAREA Element

| Attribute | Domain        | Special Handling                                                                        |
| --------- | ------------- | --------------------------------------------------------------------------------------- |
| id        | String values | ? Remove spaces, convert chars                                                          |
| class     | String values | Any prefixing or postfixing should add a space for padding to avoid merged class names. |

IMG Elem

### INPUT Elements

| HTML Element | Attribute           | Domain                                       |
| ------------ | ------------------- | -------------------------------------------- |
| input        | type                | Predefined types (text, email, number, etc.) |
| input        | min/max             | Numeric or date/time range                   |
| input        | pattern             | Regular expression                           |
| input        | maxlength/minlength | Numeric values                               |
| input        | step                | Numeric or date/time increment               |
| input        | required            | Boolean (true/false)                         |
| input        | disabled            | Boolean (true/false)                         |
| input        | value               | String                                       |

SELECT Element

| Attribute | Domain               |
| --------- | -------------------- |
| multiple  | Boolean (true/false) |

TEXTAREA Element

| Attribute           | Domain         |
| ------------------- | -------------- |
| maxlength/minlength | Numeric values |
| placeholder         | String         |

IMG Element

| Attribute | Domain                                                     |
| --------- | ---------------------------------------------------------- |
| srcset    | List of image URLs with width or pixel density descriptors |
| sizes     | List of media condition and image size pairs               |

A, AREA, LINK Elements

| Attribute | Domain    |
| --------- | --------- |
| href      | Valid URL |

VIDEO Element

| Attribute | Domain               |
| --------- | -------------------- |
| src       | Valid URL            |
| controls  | Boolean (true/false) |
| autoplay  | Boolean (true/false) |

AUDIO Element

| Attribute | Domain               |
| --------- | -------------------- |
| src       | Valid URL            |
| controls  | Boolean (true/false) |
| autoplay  | Boolean (true/false) |







I have created the table listing HTML elements and their attributes, along with the specific domains of valid inputs. You can copy this table directly into your GitBook.

If you need further customization or additional entries, feel free to ask!







## Notes&#x20;

HTML elements have a variety of attributes that define how they behave and what kind of data they can accept. Some of these attributes have specific domains of valid inputs, meaning they accept only certain types or ranges of values. Below is an overview of how these attributes are categorized and a general classification of the types of rules they must adhere to.

#### 1. **Input Elements with Specific Attribute Domains**

**a. `input` Elements:**

* **`type` Attribute:** Determines the kind of data the input element accepts. Common types include:
  * `text`, `password`, `email`, `url`, `number`, `tel`, `date`, `time`, `checkbox`, `radio`, `file`, etc.
  * **Domain:** Specific to each type (e.g., `email` requires a valid email format, `number` requires a numeric value).
* **`min` and `max` Attributes:**
  * **Domain:** Used with `type="number"`, `type="range"`, `type="date"`, `type="time"`, etc. Specifies a numeric range or date/time range.
* **`pattern` Attribute:**
  * **Domain:** A regular expression that the input value must match.
* **`maxlength` and `minlength` Attributes:**
  * **Domain:** Numeric values specifying the minimum or maximum number of characters allowed.
* **`step` Attribute:**
  * **Domain:** Specifies the increment for numeric or date/time values. Used with `type="number"`, `type="range"`, etc.

**b. `select` Element:**

* **`multiple` Attribute:**
  * **Domain:** Boolean attribute that, if present, allows multiple options to be selected.

**c. `textarea` Element:**

* **`maxlength` and `minlength` Attributes:** Similar to `input`.

#### 2. **Custom Attributes with Specific Domains**

Some HTML elements have custom attributes with specific domains:

**a. `img` Element:**

* **`srcset` Attribute:**
  * **Domain:** A list of image URLs with optional width or pixel density descriptors.
* **`sizes` Attribute:**
  * **Domain:** A list of media condition and image size pairs.

**b. `meta` Element:**

* **`charset` Attribute:**
  * **Domain:** A single character encoding name (e.g., `UTF-8`).

**c. `a`, `area`, `link` Elements:**

* **`href` Attribute:**
  * **Domain:** A valid URL.

#### 3. **Categorization of Rules for Valid Inputs**

The rules for valid inputs can be broadly classified into the following categories:

1. **Format-Based Rules:**
   * Certain attributes like `type="email"` or `pattern` enforce specific formats (e.g., an email address must contain an "@" and a domain).
2. **Range-Based Rules:**
   * Attributes like `min`, `max`, and `step` enforce numeric or date ranges.
3. **Length-Based Rules:**
   * Attributes like `maxlength` and `minlength` enforce the length of the input (e.g., the number of characters).
4. **Enumerated Values:**
   * Some attributes require a value from a predefined set (e.g., `type` in `input` can only be certain values like `text`, `email`, etc.).
5. **Boolean Attributes:**
   * Some attributes are boolean, meaning they are either present or not (e.g., `required`, `disabled`).
6. **URL Rules:**
   * Attributes like `href` and `src` must follow valid URL syntax.

#### 4. **Comprehensive Listing and Reference**

To get a complete and detailed reference:

* **MDN Web Docs** is an excellent resource for exploring HTML elements and their attributes with detailed explanations of valid input domains.
* **HTML Living Standard (WHATWG)** provides the most up-to-date and comprehensive specifications for HTML elements and their attributes.

#### 5. **Validation and Browser Behavior**

Browsers typically provide built-in validation for these attributes. For example:

* If an `input` element with `type="email"` does not contain a valid email address, the browser will prevent form submission.
* If `min`, `max`, or `step` are used, the browser will ensure that input values adhere to these constraints.

These rules ensure that the data submitted via forms is consistent, valid, and fits within expected parameters, improving both user experience and data integrity.

