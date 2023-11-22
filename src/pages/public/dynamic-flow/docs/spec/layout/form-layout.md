---
title: Form Layout
---

# Form Layout



Embed a schema inside the layout's structure.

Form Layout is used to better control how layouts and schemas are displayed by allowing them to be interleaved.

Layouts can be displayed before or after a top-level schema, but not in-between child schemas.

Schemas in the layout structure will be combined with schemas in schemas as if there's an [All Of Schema](../schema/all-of-schema#All-Of-Schema) Schema surrounding them.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `control`
* String
* No
*
  Specify a particular control to use to represent the layout. If the control is unknown, it will be ignored.
---
* `margin`
* [Size](../misc/size#Size)
* No
*
  The vertical margin to apply above this component. Defaults to `md`.
---
* `schemaId`
* String
* Yes
*
  The schema that should be embedded in this place in the layout. It must be the ID of a schema at the top level of the `schemas` array.
---
* `type`
* String
* Yes
*
  It must be `form`.
{% /table %}
