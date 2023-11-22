---
title: Paragraph Layout
---

# Paragraph Layout



A block of plain text. For richer formatting and layout options consider using [Markdown Layout](markdown-layout#Markdown-Layout).

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `align`
* [Align](../misc/align#Align)
* No
*
  The text alignment of the content. Default to `left`.
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
* `text`
* String
* Yes
*
  The user-facing string to use as the content.
---
* `type`
* String
* Yes
*
  It must be `paragraph`.
{% /table %}
