---
title: Array Schema
---

# Array Schema



Represents an array of data in the submission.

Arrays are either a list or a tuple:

- A list is a set of fields which can be repeated a number of times, with each set being an element in the array.
- A tuple is a fixed set of fields, where each field corresponds to an element in the array.

## Subtypes

### List



A variable length array where each item matches the items JSON schema. This can be used, for example, to create a
repeating form section, or multi-file upload.

#### Properties

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
* `addItemTitle`
* String
* Yes
*
  The title for the add a new item, and the title for the screen to enter the item info.
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
* `editItemTitle`
* String
* Yes
*
  The title for the screen to edit the item info.
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
* `items`
* [Schema](schema#Schema)
* Yes
*
  A schema which describes the structure of each array element.
---
* `keywords`
* Array<String>
* No
*
  A list of keywords that can be used when searching or filtering items in a [One Of Schema](one-of-schema#One-Of-Schema). Only applies when this schema is child schema in a [One Of Schema](one-of-schema#One-Of-Schema).
---
* `maxItems`
* Int
* No
*
  The maximum number of items in the array.
---
* `minItems`
* Int
* No
*
  The minimum number of items in the array.
---
* `persistAsync`
* [PersistAsync](../feature/persist-async#Persist-Async)
* No
*
  
---
* `summary`
* [Summary.Summariser](../feature/summary#Summariser)
* No
*
  Configure how this schema will be summarised when included in an [Array Schema](array-schema#Array-Schema).
---
* `title`
* String
* No
*
  A user-facing title for the schema.
---
* `type`
* String
* Yes
*
  It must be `array`.
---
* `validationAsync`
* [ValidateAsync](../feature/validate-async#Validate-Async)
* No
*
  
{% /table %}
### Tuple



A fixed-length array where each schema represents the data at the corresponding element in the array.

The minItems and maxItems validation has no purpose for a tuple, and should be ignored if provided.

#### Properties

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
* `items`
* Array<[Schema](schema#Schema)>
* Yes
*
  An array of schemas which define each element that appears in this array.
---
* `keywords`
* Array<String>
* No
*
  A list of keywords that can be used when searching or filtering items in a [One Of Schema](one-of-schema#One-Of-Schema). Only applies when this schema is child schema in a [One Of Schema](one-of-schema#One-Of-Schema).
---
* `persistAsync`
* [PersistAsync](../feature/persist-async#Persist-Async)
* No
*
  
---
* `summary`
* [Summary.Provider](../feature/summary#Provider)
* No
*
  Configure how this schema will be summarised when included in an [Array Schema](array-schema#Array-Schema).
---
* `title`
* String
* No
*
  A user-facing title for the schema.
---
* `type`
* String
* Yes
*
  It must be `array`.
---
* `validationAsync`
* [ValidateAsync](../feature/validate-async#Validate-Async)
* No
*
  
{% /table %}
