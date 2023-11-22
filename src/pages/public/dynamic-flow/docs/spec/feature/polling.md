---
title: Polling
---

# Polling



Polling instructs the client to periodically make an HTTP GET request to the specified URL and eventually trigger an action.

Polling is typically used alongside [External](external#External). For example, a step may first open an external URL and then poll for a server state change.
The client may continue to another step or end the flow.

### Example

Given the step below, the client will start making requests to the specified URL every 5 seconds.

If the response is a json object with an `action` property, for instance `{ action: { url: "/next-step", "data": "all-ok" } }`, then the action is "executed". This usually loads the next step, or exits the flow.

If the response body is not a json object with an `action` property, but the status code is 2xx, then the client continues to make requests until an `action` is found or `maxAttempts` is reached.

```kt
Step.build {
    layout { }
    polling {
        url = "https://bar.foo/status?id=12345"
        interval = 5
        maxAttempts = 100
        onError {
            action {
                exit = true
                result = encodeToJsonElement(mapOf("exit-action-data" to "EXIT!!!"))
            }
        }
    }
}
```

#### Error handling

Given the above step, the action in the `onError` object is triggered if:

- the response status code is a failure (>=400).
- the number of attempts exceeds the specified `maxAttempts`

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `interval`
* Int
* Yes
*
  The time interval between requests, in seconds.
---
* `maxAttempts`
* Int
* Yes
*
  The maximum number of requests that may be attempted, before triggering the [onError] action.
---
* `onError`
* [Polling.OnError](polling#On-Error)
* Yes
*
  An object with one action property to be triggered when polling fails.
---
* `url`
* String
* Yes
*
  The URL to open.
{% /table %}
## Related Types

### On Error




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
  The [Action](action#Action) to be triggered when polling fails.
{% /table %}
