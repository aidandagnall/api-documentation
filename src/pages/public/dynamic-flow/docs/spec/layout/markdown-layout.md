---
title: Markdown Layout
---

# Markdown Layout



A block of markdown content.

Markdown is a block of rich content defined using markdown. If you just need plain text, consider using [Paragraph Layout](paragraph-layout#Paragraph-Layout) Layout.

The following subset of markdown features are supported:
- Heading
- List (both ordered and unordered)
- Emphasis
- Strong Emphasis
- Links

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
* `content`
* String
* Yes
*
  The markdown-formatted string to use as the content.
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
  It must be `markdown`.
{% /table %}
