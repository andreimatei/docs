---
title: Data Types
toc: false
---

CockroachDB supports the following data types. Click a type for more details.

Type | Description | Example
-----|-------------|--------
[`INT`](int.html) | A 64-bit signed integer. | `12345`
[`DECIMAL`](decimal.html) | An exact, fixed-point number. | `DECIMAL '1.2345'`
[`FLOAT`](float.html) | An inexact, floating-point number. | `1.2345`
[`BOOL`](bool.html) | A Boolean value. | `true` 
[`DATE`](date.html) | Year, month, day. | `DATE '2016-01-25'`
[`TIMESTAMP`](timestamp.html) | A date and time pairing. | `TIMESTAMP '2016-01-25 10:10:10'`
[`INTERVAL`](interval.html) | A span of time. | `INTERVAL '2h30m30s'`
[`STRING`](string.html) | A string of characters. | `'a1b2c3'`
[`BYTES`](bytes.html) | A string of binary characters. | `b'\141\061\142\062\143\063'`