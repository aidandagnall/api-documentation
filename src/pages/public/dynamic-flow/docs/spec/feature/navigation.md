---
title: Navigation
---

# Navigation



Allows configuration of how navigating between steps should happen.

For example, it can be used to control what happens when the user navigates back from a step.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `back`
* [Navigation.BackBehaviour](navigation#Back-Behaviour)
* No
*
  Configure custom back behaviour which overrides any native back behaviour of the client.
{% /table %}
## Related Types

### Back Behaviour



Describes how back navigation should be handled.

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `action`
* [Action](action#Action)
* Yes
*
  The [Action](action#Action) triggered when the user navigates back. Note that this action will not validate the model against the schema before submitting.
---
* `title`
* String
* No
*
  A title describing the back action.
{% /table %}
