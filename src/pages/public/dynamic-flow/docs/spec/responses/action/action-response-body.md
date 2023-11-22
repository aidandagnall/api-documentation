---
title: Action Response Body
---

# Action Response Body



Represents an action response body.

A response is determined to be an Action when the status code is in the 200-299 range, the `exit` property in the
triggering action was not set to `true`, and the `X-DF-Response-Type: action` header is provided.

When this response is received, the client performs the provided action. When doing so the client doesn't run any
validation and no additional data from the step is included in the submission - any submission data must
be provided in the action's `data` property. See [Action](../../feature/action#Action).

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `action`
* [Action](../../feature/action#Action)
* Yes
*
  The action to perform when this response is received.
{% /table %}
