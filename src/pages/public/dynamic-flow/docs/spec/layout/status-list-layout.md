---
title: Status List Layout
---

# Status List Layout



A list of items with statuses.


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
* Array<[StatusListLayout.Item](status-list-layout#Item)>
* Yes
*
  Array of items.
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
  The user-facing title.
---
* `type`
* String
* Yes
*
  It must be `status-list`.
{% /table %}
## Related Types

### Item



A single entry in a [Status List Layout](status-list-layout#Status-List-Layout).

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `description`
* String
* No
*
  A user-facing description.
---
* `icon`
* [Icon](../misc/icon#Icon)
* Yes
*
  An icon to represent the item.
---
* `status`
* [StatusListLayout.Status](status-list-layout#Status)
* No
*
  The status of the item, if it has one.
---
* `title`
* String
* Yes
*
  A user-facing title.
{% /table %}
### Status



Represents the state of an item in a [Status List Layout](status-list-layout#Status-List-Layout).

#### Values

| Value | Description |
| ---| --- |
| `done` | The item is complete. |
| `not-done` | The item has not been started or is waiting for input from the user. |
| `pending` | The item is in progress and no input is needed from the user. |

