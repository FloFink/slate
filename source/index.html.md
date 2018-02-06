---
title: Prescreen API

language_tabs:
  - json

toc_footers:
  - <a href='v1/testing-interface'>Visit testing interface</a>

includes:
  - endpoints

search: true
---


# Introduction
Welcome to the Prescreen REST API. You can use this API to export and import data about candidates, applications and jobs.

This document explains the general behaviour of our API, and provides a list of available API operations, and their expected input and output.

### Testing interface
In addition to this documentation, we also provide a [testing interface](v1/testing-interface), which allows you to make API requests directly from your browser.

It also documents individual input fields in more detail, with information such as allowed values and format constraints. 

# Authentication
In order to make any request to the API, you have to specify a valid api key as a HTTP header with the name `apikey`.
### Example
`apikey: 11111111aaaaaaaa22222222bbbbbbbb`


If the key is not specified or invalid, the API will respond with a status code `401` or `403` respectively.

## How to get a key
The Prescreen app offers an interface to create and remove API keys. To find this interface, open your account settings and navigate to *"Integration"* > *"REST API"*.
Only admin users have permission to do this.

# General behaviour

## Format
All data in request and response bodies is encoded in JSON format.
Please refer to the documentation of individual endpoints for the expected input and output schema of an operation.

## Response on errors

> Exaple of an error response body

```json
{
  "message": "unable to decode json"
}
```

When an error occurs during an operation, the API will respond with a status code starting with `4xx` or `5xx`.
In this case, the response body will contain a JSON with a `message` field, describing what went wrong.

Additional fields may be included, depending on the type of the error and where it happened.

### Examples for error codes

Error Code | Meaning
---------- | -------
400 | Bad Request -- there is something wrong with the request body
401 | Unauthorized -- `apikey` header is not set
403 | Forbidden -- key is invalid
404 | Not Found -- you attempted to access a resource that does not exist
500 | Internal Server Error -- an unexpected error occured

## Queries
API-Operations that respond with a list of items generally allow to specify query parameters to filter the results by a specific field (see individual endpoint documentation for accepted parameters).

Additionally, when querying for strings, the `%` character is allowed as a wildcard. It will match any sequence of characters including the empty string.
For example, the (url encoded) string

`.../candidate?profile[lastname]=%Muster%` 

will match any candidates with last name “Muster”, “Mustermann”, etc.

## Pagination

> Exaple of a query response

```json
{
  "data": [
    {},
    {},
    {}
  ],
  "links": {
    "self": "someUrl?page_size=3&page=1",
    "first": "someUrl?page_size=3&page=1",
    "prev": null,
    "next": "someUrl?page_size=3&page=2",
    "last": "someUrl?page_size=3&page=14",
  }
}
```

The above mentioned query operations also accept two parameters for controlling pagination:

Parameter | Description | Remarks
--------- | ----------- | -------
page | The page number you want to navigate to | Default: 1
page_size | Number of items to fetch per page | Default: 10, Maximum: 100

### Navigation links
More specifically, the response of such requests will contain a `data` field, which stores the list of selected items, and a `links` field, which can be used to navigate pages:

Field name | Description | Remarks
---------- | ----------- | -------
self | Link to this page | Null if query result is empty
first | Link to first page | Null if query result is empty
prev | Link to previous page | Null if currently on first page
next | Link to next page | Null if currently on last page
last | Link to last page | Null if query result is empty

## PATCH requests
The API allows to update specific fields of an object individually, without making changes to other fields. It implements RFC 7396 (JSON Merge Patch) for this.

This means you can simply pass a subset of the JSON schema of an object to the API, containing all fields that you want to change. All fields not contained in this subset will remain unchanged.

If you update arrays, only array elements you specified will be present after the update, all others will be deleted.

## Files
All files are embedded in the JSON objects as Base64-encoded strings (for both input and output). Additional information (such as the filename) can be specified depending on the operation.

### Deactivate file output
In case you want to exclude encoded files from a response, you can do so by setting a specific header in your request:

`X-Prescreen-Include-Encoded-Files: false`

If this is set to `false`, any field that usually holds Base64-encoded data will instead be `null`.

## Date format
All dates are formatted in the ISO-8601 format `Y-m-d\TH:i:sO` (date, time and timezone).

### Example: 

`1989-08-15T15:22:59+0000`

# Additional notes

## CV Parsing

Our API offers a way to automatically parse a candidate's profile data from a cv file (see field `cv_file` in candidate endpoints).
Since parsed data is set **after** all other fields, some of the data you specified may be overwritten during parsing.

Allowed file types for CVs are **doc**, **docx**, **pdf** and **rtf**.

<aside class="notice">
Please note that this feature is intended to be used when registering new candidates (e.g. via a custom registration form), <b>not</b> for bulk importing candidates from previous systems.
<br><br>Within the bounds of <b>fair-use</b>, CV parsing is free of charge. However, excessive or unjustified use may lead to additional fees per request. If this should be the case, we will inform you before any fees apply.
</aside>

## Avatar pictures

When setting a candidate's avatar picture, only square images are accepted (images with mismatching width and height will be rejected).

Allowed file types are **jpg**, **png**, **bmp** and **gif**.
