---
title: Validate Async
---

# Validate Async



Validation Async allows you to validate the value of a field on change by calling an endpoint.

This allows for more complex validation than is possible using local validation rules.

When the value of a schema with a [Validate Async](validate-async#Validate-Async) configuration changes, first any local validation
is run. If this local validation passes, a request is sent to the URL defined at [url],
where the request body is a JSON object containing the value of the field under a property matching
the value of [param].

On success, the server should respond with a `2xx` status code and either an empty body, in which
case no feedback is given to the user, or a JSON body with a `message` property, which will be shown
to the user. On failure, the server should respond with a `422` status code and a JSON body with
a `message` property which will be shown to the user.

**Note that "failed" validation does not prevent the client from submitting the step in the case of async validation.**

Also, in the case where the validation-async network call fails or returns an unexpected response,
the client ignores the problem and allows the user to submit.

For these reasons, any validation which is critical should also be performed by the server on submission.

### Example

Given a schema defined as:

```kt
string {
    title = "IBAN"
    validationAsync = ValidateAsync(
        param = "iban",
        method = HttpMethod.POST,
        url = "/validate-iban"
    )
}
```

When the user enters a value, e.g. "NL30ABNA7619995846", a `POST` request would be made to the `/validate-iban` endpoint with the following body:

```json
{
  "iban": "NL30ABNA7619995846"
}
```

On success, the server responds with a `200` status code and the response body should either be empty, in which case no feedback will be given to the user, or a JSON body with the following structure:

```json
{
  "message": "Valid IBAN"
}
```

In which case the message will be displayed to the user to let them know the value they have entered is valid.

On failure, the server should respond with a `422` status code and a json body giving a message to display to the user:

```json
{
  "message": "This IBAN is invalid. Please check it again."
}
```

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `method`
* String
* Yes
*
  The HTTP method to use for the request. Only methods which allow a request body are supported.
---
* `param`
* String
* Yes
*
  The name of the property under which the value of the schema will be sent in the request body.
---
* `url`
* String
* Yes
*
  The URL to use for the request.
{% /table %}
