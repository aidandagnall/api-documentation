---
title: Schema
---

# Schema



The data to be collected, its validation rules, and how it is presented to the user are defined through a subset of
[JSON Schema](https://json-schema.org/),
with some additional properties added to improve the user experience and functionality. Each form step contains an
array of schemas - typically there would only be one root schema but in order to support more layouts
it's possible to provide any number. These schemas are mapped to their corresponding input components to be presented to
the user, for example, a string schema would be mapped to a text input.

At submission time, the values entered for each root schema are merged and submitted to the endpoint
defined by the [Action](../feature/action#Action) the user has taken. In the case of any conflicting definitions,
schemas which appear later in the schemas array will overwrite any values from schemas earlier in the array.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `$id`
* String
* No
*
  A unique id which can be used to refer to the schema.
---
* `alert`
* [AlertLayout](../layout/alert-layout#Alert-Layout)
* No
*
  Configure an alert which will be displayed above the UI for this schema. This can be used to provide warnings or additional information to the user, but shouldn't be used for validation. For client-side validation please see the validation available on each schema type, or see [Validate Async](../feature/validate-async#Validate-Async) and [Action](../feature/action#Action) for server-side validation.
---
* `analyticsId`
* String
* No
*
  An internal id which is attached to analytics events relating to the schema. This is not user-facing and does not have to be unique within the step.
---
* `control`
* String
* No
*
  An identifier which can be used to request the client use a particular UI control to represent this schema.
---
* `description`
* String
* No
*
  A user-facing description for the schema.
---
* `disabled`
* Boolean
* No
*
  If true, the UI for this schema will not accept input, but the corresponding data will still be submitted.  Defaults to false.
---
* `hidden`
* Boolean
* No
*
  If true, no UI will be shown to the user for this schema, but the corresponding data will still be submitted. Defaults to false.
---
* `icon`
* [Icon](../misc/icon#Icon)
* No
*
  An icon which the client can use to represent this schema.
---
* `image`
* [ImageLayout](../layout/image-layout#Image-Layout)
* No
*
  An image which the client can use to represent this schema.
---
* `keywords`
* Array<String>
* No
*
  A list of keywords that can be used when searching or filtering items in a [One Of Schema](one-of-schema#One-Of-Schema). Only applies when this schema is child schema in a [One Of Schema](one-of-schema#One-Of-Schema).
---
* `summary`
* [Summary](../feature/summary#Summary)
* No
*
  Configure how this schema will be summarised when included in an [Array Schema](array-schema#Array-Schema).
---
* `title`
* String
* No
*
  A user-facing title for the schema.
{% /table %}
## Subtypes

| Type | Description |
| --- | --- |
| [All Of Schema](all-of-schema#All-Of-Schema) | A schema which merges the value of its child schemas. |
| [Array Schema](array-schema#Array-Schema) | Represents an array of data in the submission. |
| [Blob Schema](blob-schema#Blob-Schema) | Represents a binary data submission using Form Data rather than JSON. |
| [Boolean Schema](boolean-schema#Boolean-Schema) | Represents a boolean value in the submission. |
| [Const Schema](const-schema#Const-Schema) | Represents a constant value in the submission. |
| [Integer Schema](integer-schema#Integer-Schema) | Represents a numeric value which must be a whole number. For floating point numbers, use a [Number Schema](number-schema#Number-Schema) instead. |
| [Number Schema](number-schema#Number-Schema) | Represents any numeric value - either an integer or a floating point number. |
| [Object Schema](object-schema#Object-Schema) | Represents an object value in the submission. |
| [One Of Schema](one-of-schema#One-Of-Schema) | Offers a choice between a number of child schemas. |
| [String Schema](string-schema#String-Schema) | Represents a string value in the submission. |

