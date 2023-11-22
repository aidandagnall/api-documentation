---
title: Review Layout
---

# Review Layout



A list of read-only fields used to show information to the user for review.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `callToAction`
* [ReviewLayout.CallToAction](review-layout#Call-To-Action)
* No
*
  A titled [Action](../feature/action#Action) which can be performed by the user
---
* `control`
* String
* No
*
  Specify a particular control to use to represent the layout. If the control is unknown, it will be ignored.
---
* `fields`
* Array<[ReviewLayout.Field](review-layout#Field)>
* Yes
*
  The fields to be reviewed.
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
  Title for the review block.
---
* `type`
* String
* Yes
*
  It must be `review`.
{% /table %}
## Related Types

### Field



A single field in a [Review Layout](review-layout#Review-Layout)

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `help`
* [Help](../feature/help#Help)
* No
*
  Provide additional help information to the user.
---
* `label`
* String
* Yes
*
  The user-facing label.
---
* `value`
* String
* Yes
*
  The user-facing value.
{% /table %}
### Call To Action



Adds an [Action](../feature/action#Action) to the review layout. For example, it could be used to provide an edit action.

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
  The [Action](../feature/action#Action) which should be performed.
---
* `title`
* String
* Yes
*
  A user-facing title.
{% /table %}
