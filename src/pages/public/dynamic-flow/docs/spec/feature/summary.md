---
title: Summary
---

# Summary



Summary specifies a configuration to produce user-facing copy for child schemas of [List](../schema/array-schema#List).

Default values may be specified to be used if values are not provided on child schemas.

## Subtypes

### Provider



A schema which provides values for the summary.

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `providesDescription`
* Boolean
* No
*
  If true, the value of this schema can be used as a summary description.
---
* `providesIcon`
* Boolean
* No
*
  If true, the icon of this schema can be used as a summary icon.
---
* `providesImage`
* Boolean
* No
*
  If true, the image of this schema can be used as a summary image.
---
* `providesTitle`
* Boolean
* No
*
  If true, the value of this schema can be used as a summary title.
{% /table %}
### Summariser



A schema which summarises its child schemas.

Default values can be specified for the summary if values are not provided by its child schemas.

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `defaultDescription`
* String
* No
*
  A description to be used for the summary if a description is not provided by a child schema.
---
* `defaultIcon`
* [Icon](../misc/icon#Icon)
* No
*
  An icon to be used for the summary if an icon is not provided by a child schema.
---
* `defaultImage`
* [ImageLayout](../layout/image-layout#Image-Layout)
* No
*
  An image to be used for the summary if an image is not provided by a child schema.
---
* `defaultTitle`
* String
* No
*
  A title to be used for the summary if a title is not provided by a child schema.
---
* `providesDescription`
* Boolean
* No
*
  If true, the value of this schema can be used as a summary description.
---
* `providesIcon`
* Boolean
* No
*
  If true, the icon of this schema can be used as a summary icon.
---
* `providesImage`
* Boolean
* No
*
  If true, the image of this schema can be used as a summary image.
---
* `providesTitle`
* Boolean
* No
*
  If true, the value of this schema can be used as a summary title.
{% /table %}
