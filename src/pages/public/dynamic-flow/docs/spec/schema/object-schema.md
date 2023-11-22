---
title: Object Schema
---

# Object Schema



Represents an object value in the submission.

Objects can optionally be given a title to have them appear as form sections.

If you'd like to group your fields into separate sections while keeping them in the same object in your submission,
consider using [All Of Schema](all-of-schema#All-Of-Schema).

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
* `displayOrder`
* Array<String>
* Yes
*
  The order in which the properties should be rendered by the client. This is required because objects are inherently unordered, and all properties must be included or they will not be displayed.
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
* `properties`
* Map<String, [Schema](schema#Schema)>
* Yes
*
  The properties of the object.
---
* `required`
* Array<String>
* No
*
  An array containing the names of the properties which must have a non-null value for the object to be valid.
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
  It must be `object`.
{% /table %}
