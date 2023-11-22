---
title: Step Error
---

# Step Error



Errors which can be displayed to the user, either in response to a step submission or on step load.

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
  A general error message, not related to any particular schema.
---
* `validation`
* Any
* No
*
  Error messages related to specific fields. The structure of this value must match the structure of the data to be validated. For example, given the following model: ``` {   "name": "A Person",   "bankDetails": {     "accountNumber": "31510604",     "sortCode": "100000"   } } ``` A validation message for the "sortCode" field should be provided as follows: ``` {   "bankDetails": {     "sortCode": "Please enter a valid sort code"   } } ``` Multiple validation messages can be returned at once, for example: ``` {   "name": "Please enter a full name",   "bankDetails": {     "sortCode": "Please enter a valid sort code"   } } ```
{% /table %}
