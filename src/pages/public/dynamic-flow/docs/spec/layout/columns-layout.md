---
title: Columns Layout
---

# Columns Layout



Allows content to be displayed in two columns.

If screen space is limited, the contents will be collapsed into a single column.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `bias`
* [ColumnsLayout.Bias](columns-layout#Bias)
* No
*
  Indicates which column, if any, will be given more visual weight. Defaults to `none`.
---
* `control`
* String
* No
*
  Specify a particular control to use to represent the layout. If the control is unknown, it will be ignored.
---
* `left`
* Array<[Layout](layout#Layout)>
* Yes
*
  An array of layout components to display in the left column.
---
* `margin`
* [Size](../misc/size#Size)
* No
*
  The vertical margin to apply above this component. Defaults to `md`.
---
* `right`
* Array<[Layout](layout#Layout)>
* Yes
*
  An array of layout components to display in the right column.
---
* `type`
* String
* Yes
*
  It must be `columns`.
{% /table %}
## Related Types

### Bias



Values for the bias property.

#### Values

| Value | Description |
| ---| --- |
| `left` | The left column will be given more visual weight |
| `none` | Both columns will have equal visual weight |
| `right` | The right column will be given more visual weight |

