---
title: Link Handler
---

# Link Handler



A pattern which is matched against any incoming universal links, with an action to trigger when the pattern is matched.

Link handling is typically used alongside [External](external#External).

### Action Data

When the action is performed, the payload will contain all the data usually submitted with an action. Additionally,
the data will be merged with an object containing the following structure:

```json
{
    "url": "https://wise.com/some-url"
}
```

Where "https://wise.com/some-url" is the full URL that was matched against the pattern.

### Example

Given the step below, the client will listen for any deep or universal links that are used to open the app.

```kt
Step.build {
    layout { }
    linkHandlers = listOf(
        LinkHandler(
            regexPattern = """https:\/\/wise.com\/success-callback.""",
            action = Action.build {
                url = "/handle-success-callback"
                data = encodeToJsonElement(mapOf("some-additional-data" to true))
            }
        ),
        LinkHandler(
            regexPattern = """https:\/\/wise\.com\/failure-callback.*""",
            action = Action.build {
                url = "/handle-failure-callback"
            }
        )
    )
}
```

If the user is on this step and then opens a universal or deep link, it'll be matched against the patterns
in the array, and any matching action will be executed.

For example, if the user opens the app with the universal link "https://wise.com/success-callback?token=1234",
this will be matched against the first pattern in the array. The corresponding action will be executed, and
the payload will also contain the url that was matched - for example in this case the following data
would be submitted to "/handle-success-callback":

```json
{
    "some-additional-data": true,
    "url": "https://wise.com/success-callback?token=1234"
}
```

If a link is opened which doesn't match any of the patterns then no action is taken.

## Properties

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
  An action to be triggered when the regex pattern is matched.
---
* `regexPattern`
* String
* Yes
*
  A regex pattern to be matched against any incoming universal links.
{% /table %}
