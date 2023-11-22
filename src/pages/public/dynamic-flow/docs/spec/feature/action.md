---
title: Action
---

# Action



An action may be performed by the user when submitting a step. Actions can submit to an endpoint, progress the flow, or exit the flow.

An action typically defines its URL and HTTP method to submit step data, and can optionally indicate that on success
this action will end the flow.

An endpoint can respond to a submitting action with an error status code and the standard error response format in order to display errors to the user.

### Behaviour

#### Non-Exiting Actions

If an action does not specify the `exit` property as true, it is expected that the action will submit the step payload.
For example, the following action is a non-exiting action.

```kt
action {
    url = "/submitForm"
    method = HttpMethod.POST
}
```

#### Exiting Actions

If an action specifies `exit` as `true`, it is expected that this action should terminate the flow. For exiting actions,
the `url` property is optional.

#### Submitting Exiting Actions

If the `url` property is specified, the step payload will be submitted. On a successful response, the `result` property of the action (if provided)
will be merged with the response to the submission, and that combined result will be used as the result of the flow, which will terminate. In case
of any conflicts in the merge, the value of the result property of the action takes precedence.

#### Non-Submitting Exiting Actions

If the `url` property is not specified, when the action is taken the flow will be terminated and the value of the result
property will be used as the result of the flow.

##### Example

Given the following action:

```kt
action {
    exit = true
    result = encodeToJsonElement(mapOf(
        "someKey" to "somveValue"
    ))
}
```

When this action is taken, the flow will be completed and the result of the flow will be:

```json
{
  "someKey": "someValue"
}
```

#### Actions Which Sometimes Exit

In some cases, the provider of the step will not know if a submitting action will exit. For example, depending on the data entered by the user,
the flow may be complete, or we may need to ask them some follow-up questions. In these cases the `exit` property shouldn’t be specified. Instead,
the response to the submission should include an `X-DF-Response-Type: exit` header. When the client receives this header
in the response, it will continue in the same way as it would for a submitting exiting action. See [Response](../responses/response#Response).

#### Summary

This tree summarises the possibile paths an action can lead to:

- If `exit` is `true`:
  - If `url` is `null`:
    - Exit flow with value of `result`
  - If `url` is non-null:
    - Submit to `url`
    - Merge value of `result` into response body
    - Exit flow with the merged result
- If `exit` is `false`:
  - Submit to `url`
  - If response has header `X-DF-Response-Type: "exit"`:
    - Merge value of `result` into response body
    - Exit flow with the merged result
  - If response does not have header `X-DF-Response-Type: "exit"`:
    - The response is handles as normal

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `data`
* Any
* No
*
  An object to be merged with the step data before submission.
---
* `exit`
* Boolean
* No
*
  See 'Exiting Actions'.
---
* `id`
* String
* No
*
  A unique id which can be used for analytics purposes.
---
* `method`
* String
* No
*
  The HTTP method to use for the async submission. Defaults to POST.
---
* `result`
* Any
* No
*
  See 'Exiting Actions'.
---
* `skipValidation`
* Boolean
* No
*
  Indicates that the action should not trigger client-side validation.
---
* `timeout`
* Int
* No
*
  Suggested 'timeout' duration, in seconds, for the network request resulting from this action. Typically used when the endpoint is expected to take a long time to respond.
---
* `url`
* String
* No
*
  The URL to use for the submission.
{% /table %}
