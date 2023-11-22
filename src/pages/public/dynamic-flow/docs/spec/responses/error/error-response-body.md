---
title: Error Response Body
---

# Error Response Body



Represents an error response body.

A response is determined to be an error when the status code of a response is outside of the 200-299 range.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `error`
* String
* No
*
  A user-facing, general error message, not related to any particular schema.
---
* `refreshUrl`
* String
* No
*
  If present, the client will refresh the step using the given URL. Any errors also present in the response should be applied to the refreshed step. See [Refresh On Change](../../feature/refresh-on-change#Refresh-On-Change).
---
* `validation`
* Any
* No
*
  Error messages related to specific fields. The structure of this value must match the structure of the data to be validated. For example, given the following model: ``` {   "name": "A Person",   "bankDetails": {     "accountNumber": "31510604",     "sortCode": "100000"   } } ``` A validation message for the "sortCode" field would be provided as follows: ``` {   "bankDetails": {     "sortCode": "Please enter a valid sort code"   } } ``` Multiple validation messages can be returned at once, for example: ``` {   "name": "Please enter a full name",   "bankDetails": {     "sortCode": "Please enter a valid sort code"   } } ```
{% /table %}
