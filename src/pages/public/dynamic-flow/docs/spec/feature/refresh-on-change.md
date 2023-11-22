---
title: Refresh On Change
---

# Refresh On Change



RefreshOnChange allows the structure of a step to change based on user input.

When a `refreshUrl` is provided on a [Step](../step/step#Step), and the value of a schema which is marked as requiring a refresh on change is changed,
the current value of the step is submitted to the URL using a POST request.

The response to this request will either be:
- A response with a status code of 304 (Not Modified). In this case no action is taken and the form is left unchanged.
- A new Step, which replaces the current step.

To allow the backend to determine if a change is required, a step response may include a string in an ETag header.
If the step response includes this header, the client must provide the same string in an If-None-Match header when making refresh on change requests.
When a refresh results in a new step, the response may include an updated ETag.
The latest ETag must always be used in subsequent refresh on change requests.
If no ETag is provided in a response then no If-None-Match header should be sent with refresh on change requests.

Note: in the case of a new Step, the value of the current step will not be carried over and the model must be sent alongside the new step.

If a refresh on change call fails, the step is considered to be in an invalid state.
In this case an error must be displayed to the user, and they should either be returned to the previous step, or the flow should be cancelled.

### Example

Given the following step:

```kt
Step.build {
    id = "refresh-example"
    title = "Refresh on Change Example"
    refreshUrl = "/refresh-endpoint"
    schemas {
        obj {
            properties {
                string("name") {
                    title = "Full Name"
                }
                oneOf("country") {
                    title = "Country"
                    refreshStepOnChange = true
                    schemas {
                        const {
                            title = "France"
                            value = JsonPrimitive("fr")
                        }
                        const {
                            title = "Germany"
                            value = JsonPrimitive("de")
                        }
                        const {
                            title = "United Kingdom"
                            value = JsonPrimitive("gb")
                        }
                    }
                }
            }
        }
    }
}
```

The `country` field has a `true` value for the `refreshStepOnChange` property. This means that when the value of the `country` field is changed, the current value of the form will be submitted to the `/refresh-endpoint` endpoint - for example if the user enters a name of "Tim Apple" has selected "United Kingdom", a `POST` request would be made to that URL with the following body:

```json
{
  "name": "Tim Apple",
  "country": "gb"
}
```

If this change of value doesn't change the structure of the form, the server can respond with a `304` status code, and the form is left unchanged.

If the form structure needs to change, for example to add a "Postcode" field, the server can respond with a `2xx` status code and a new step to replace the current one:

```kt
Step.build {
    id = "refresh-example"
    title = "Refresh on Change Example"
    refreshUrl = "/refresh-endpoint"
    model = encodeToJsonElement(mapOf(
        "name" to "Tim Apple",
        "country" to "gb"
    ))
    schemas {
        obj {
            properties {
                string("name") {
                    title = "Full Name"
                }
                oneOf("country") {
                    title = "Country"
                    refreshStepOnChange = true
                    schemas {
                        const {
                            title = "France"
                            value = JsonPrimitive("fr")
                        }
                        const {
                            title = "Germany"
                            value = JsonPrimitive("de")
                        }
                        const {
                            title = "United Kingdom"
                            value = JsonPrimitive("gb")
                        }
                    }
                }
                string("postalCode") {
                    title = "Postcode"
                }
            }
        }
    }
}
```

Note that the server is the current model alongside the step. This is to allow the server the flexibility to replace any model values if it wishes to do so - the client will not carry the old state over into the new step.

## Related Types

### Refreshable Step



Steps can be configured to support refresh on change by providing some configuration.

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `refreshUrl`
* String
* No
*
  The URL to use to fetch an updated step when the value of a schema marked refreshStepOnChange is updated.
{% /table %}
### Refresh Trigger



Used to configure the refresh on change behaviour on any schema which supports it.

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `refreshStepOnChange`
* Boolean
* No
*
  When true, the step will be refreshed when the value of this schema changes.
{% /table %}
