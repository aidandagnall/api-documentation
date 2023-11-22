---
title: Box Layout
---

# Box Layout



A container for a group of components with an optional border.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `border`
* Boolean
* No
*
  If true, a border is displayed around the box. Defaults to false.
---
* `components`
* Array<[Layout](layout#Layout)>
* Yes
*
  The contained components.
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
* `type`
* String
* Yes
*
  It must be `box`.
---
* `width`
* [Size](../misc/size#Size)
* No
*
  The width of the box. Defaults to `xl`.
{% /table %}
