---
title: Persist Async
---

# Persist Async



Persist Async allows you to submit part of a step asynchronously to an endpoint, then submit an identifier from that asynchronous submission
as part of the main step submission. This can be useful in cases where the content of a field is very large (for example file upload),
or for if you need to tokenize part of the form for security reasons (e.g. submitting card numbers to a PCI-compliant server).

This functionality is specified using the `persistAsync` property of a [Schema](../schema/schema#Schema).

Note that the schema on which the `persistAsync` property is set should reflect the value that is
submitted (i.e. the token/identifier), while the [schema] property defines
the schema that is shown to the user and submitted to the persist async endpoint.

### Example

When the value of the field changes, a request is sent to the URL defined in the `persistAsync` object, where the request body is
a JSON object containing the value of the field under a property matching the value of `persistAsync.param`.

For example, if the schema was defined as:

```kt
Step.build {
    layout { }
    schemas {
        string {
            persistAsync  {
                url = "/persistCard"
                param = "number"
                idProperty = "token"
                schema = StringSchema.build {
                    title = "Card Number"
                }
            }
        }
    }
}
```

Then a text input titled "Card Number" would be rendered in the form to represent this schema. When the user enters a card number
of "1234567890", a `POST` request would be made to the `/persistCard` endpoint with the following body:

```json
{
  "number": "1234567890"
}
```

On success, the response body should be a JSON object which contains an identifier that should be used in the main submission
under the property specified in `persistAsync.idProperty` - for example:

```json
{
  "token": "ce0a93b2-f11d-49a4-ab02-705bb66f5b39"
}
```

When the user submits the form, the submission will contain this identifier as the value of the schema.

### Error Handling

In the case of an error, the standard [Step Error](step-error#Step-Error) response can be used.

In the card example above, the server could respond as follows with a non-2xx status code to show an error
on the card number field:

```json
{
  "validation": {
    "number": "This card number is invalid"
  }
}
```

If a persist async call fails, the client should re-attempt it on the next form submission. A failure should prevent
submission and display an error to the user.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `idProperty`
* String
* Yes
*
  The name of the property under which the value used in the main submission can be found in the response body.
---
* `method`
* String
* Yes
*
  The HTTP method used for the async submission. Defaults to POST.
---
* `param`
* String
* Yes
*
  The name of the property under which the value of the schema will be sent in the request body.
---
* `schema`
* [Schema](../schema/schema#Schema)
* Yes
*
  The schema which will be shown to the user, and whose value will be sent in the Persist Async submission.
---
* `url`
* String
* Yes
*
  The URL used for the async submission.
{% /table %}
