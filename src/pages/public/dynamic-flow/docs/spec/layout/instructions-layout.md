---
title: Instructions Layout
---

# Instructions Layout



A list of fields used to inform the user of actions to do and not do.

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
* `items`
* Array<[InstructionsLayout.Item](instructions-layout#Item)>
* Yes
*
  An array of instructions.
---
* `margin`
* [Size](../misc/size#Size)
* No
*
  The vertical margin to apply above this component. Defaults to `md`.
---
* `title`
* String
* No
*
  A user-facing title.
---
* `type`
* String
* Yes
*
  It must be 'instructions'.
{% /table %}
## Related Types

### Item



A single instruction in an [Instructions Layout](instructions-layout#Instructions-Layout)

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `context`
* [Context](../misc/context#Context)
* Yes
*
  The semantics of the instruction.
---
* `text`
* String
* Yes
*
  The user-facing text for the instruction.
{% /table %}
