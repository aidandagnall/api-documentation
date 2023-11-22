---
title: Loading Indicator Layout
---

# Loading Indicator Layout



A symbol indicating an indeterminate loading or pending state, when the user should wait for something to happen.
Typically used in conjunction with [Link Handler](../feature/link-handler#Link-Handler) or [Polling](../feature/polling#Polling).

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
* `size`
* [Size](../misc/size#Size)
* No
*
  The size of the indicator. Defaults to `md`.
---
* `type`
* String
* Yes
*
  It must be 'loading-indicator'
{% /table %}
