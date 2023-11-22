---
title: Alert Layout
---

# Alert Layout



Show an attention-grabbing message.

Alerts can be used to communicate important messages to the user, drawing more attention than a standard paragraph or info layout.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `context`
* [Context](../misc/context#Context)
* No
*
  The semantics of the alert. Defaults to `neutral`.
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
* `markdown`
* String
* Yes
*
  The content of the alert as string. The following subset of markdown features are supported: Emphasis, strong emphasis.
---
* `type`
* String
* Yes
*
  It must be `alert`.
{% /table %}
