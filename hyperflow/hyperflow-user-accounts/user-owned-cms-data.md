---
description: >-
  Built simple low-volume applications which use the CMS for user-specific
  datastore.
---

# User-Owned CMS Data

## Use cases

* Built simple low-volume applications which use the CMS for user-specific datastore.&#x20;

Examples;

* Small auction site
* Simple "purchased access" management, e.g. courses, videos, etc.&#x20;

### Not suitable for

* Large user bases ( CMS item limits
* Heavily trafficked sites ( API rate limits )
* Complex data structures ( but JSON might work )&#x20;

## Design & Architecture Notes

* Uses HF WF API to perform CRUD ops
* Lists are marked with custom attributes to designate&#x20;
  * User-owned records
  * Behavior - remove | redact | readonly
* Defined UserID field in CMS to designate ownership



## Security

CSRF token

Encryption options exist&#x20;

## Optimization

* Can use JSON on a per-user record for disparate data, ideally not large lists.

## External Data Options

