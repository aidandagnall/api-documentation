---
title: Button Layout
---

# Button Layout



A component which performs an [Action](../feature/action#Action) when pressed.
You can affect the button appearance using the "control" and "context" properties.

## Properties

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
  The action to perform when the button is pressed.
---
* `context`
* [Context](../misc/context#Context)
* No
*
  The semantics of the button. Defaults to `neutral`.
---
* `control`
* String
* No
*
  Specify a particular control to use to represent the layout. Typically, values are "primary", "secondary", or "tertiary". If the control is unknown, it will be ignored.
---
* `disabled`
* Boolean
* No
*
  If `true`, user interaction is disabled. Defaults to `false`.
---
* `margin`
* [Size](../misc/size#Size)
* No
*
  The vertical margin to apply above this component. Defaults to `md`.
---
* `pinOrder`
* Int
* No
*
  pinOrder is an optional property that specifies that the button should be pinned at the bottom of the display. If multiple buttons use pinOrder, they will be ordered based on the pinOrder value in ascending order from top to bottom. Any positive or negative integer values are accepted.
---
* `title`
* String
* Yes
*
  A user-facing title.
---
* `type`
* String
* Yes
*
  It must be `button`.
{% /table %}
