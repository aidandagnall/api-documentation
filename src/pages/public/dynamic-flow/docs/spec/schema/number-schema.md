---
title: Number Schema
---

# Number Schema



Represents any numeric value - either an integer or a floating point number.
If the value should always be an integer, consider using an [Integer Schema](integer-schema#Integer-Schema) instead.

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
* `autocompleteHint`
* Array<[AutocompleteHint](../misc/autocomplete-hint#Autocomplete-Hint)>
* No
*
  A list of hints applied to a field to describe to the client what kind of field it is. This can enable the user agent or assistive technologies running to automatically suggest or fill in information specific to the user. Values not recognised by the client will be discarded, and clients that only support single values will take the first valid value in the list.
---
* `autofillKey`
* String
* No
*
  Identifies the type of data which the client can autofill for this schema. This is provided in a `.` delimited string, in the format `source.prop`, e.g `contact.email`. In this example, the client should suggest values from the `email` property on objects retrieved from the `contact` source to autofill this field. The only currently supported source is `contact`. It will inspect contacts from the native client address book (if available). Supported properties on the `contact` source are: - `givenName` - `familyName` - `fullName` - `email` - `firstLine` - `city` - `state` - `postalCode` - `countryCode`
---
* `control`
* String
* No
*
  An identifier which can be used to request the client use a particular UI control to represent this schema.
---
* `default`
* Double
* No
*
  The default value to use for this schema. This will be overridden by a value in the model of the [Step](../step/step#Step) if one is provided.
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
* `help`
* [Help](../feature/help#Help)
* No
*
  Provide additional help information to the user.
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
* `maximum`
* Double
* No
*
  The maximum value permitted, if null then there is no minimum value.
---
* `minimum`
* Double
* No
*
  The minimum value permitted, if null then there is no minimum value.
---
* `persistAsync`
* [PersistAsync](../feature/persist-async#Persist-Async)
* No
*
  
---
* `placeholder`
* String
* No
*
  A user-facing placeholder value to use for the field. This can be used to provide an example of the expected input.
---
* `refreshStepOnChange`
* Boolean
* No
*
  When true, the step will be refreshed when the value of this schema changes.
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
  It must be `number`.
---
* `validationAsync`
* [ValidateAsync](../feature/validate-async#Validate-Async)
* No
*
  
---
* `validationMessages`
* Map<String, String>
* No
*
  An object where each property/value pair is the name of a validation property (e.g. maximum) to the user-facing error message to display if the validation fails.
{% /table %}
