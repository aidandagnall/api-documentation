---
title: Decision Layout
---

# Decision Layout



A set of options which each perform an [Action](../feature/action#Action).

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
* `options`
* Array<[DecisionLayout.Option](decision-layout#Option)>
* Yes
*
  Array of options.
---
* `type`
* String
* Yes
*
  It must be `decision`.
{% /table %}
## Related Types

### Option



An option is a single entry in the decision that the user can choose.

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `action`
* [Action](../feature/action#Action)
* Yes
*
  The action to perform when selected.
---
* `description`
* String
* No
*
  A user-facing description.
---
* `disabled`
* Boolean
* No
*
  If `true`, user interaction is disabled. Defaults to `false`.
---
* `icon`
* [Icon](../misc/icon#Icon)
* No
*
  An icon to represent the option.
---
* `image`
* [ImageLayout](image-layout#Image-Layout)
* No
*
  An image to represent the option.
---
* `title`
* String
* Yes
*
  A user-facing title.
{% /table %}
