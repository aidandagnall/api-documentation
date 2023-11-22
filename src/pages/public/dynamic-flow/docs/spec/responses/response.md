---
title: Response
---

# Response



In Dynamic Flow we support four types of response. Every HTTP response must fall into one of these four types: "step", "action", "exit" or "error".

In most cases the response should contain a `X-DF-Response-Type` response header with a value of either `step`, `action`, or `exit`; this tells the client what to expect in the response body.

### Response Type Table

When the triggering action has `exit: false`:

| Response Header                | Status Code | Response Type                                             |
| ------------------------------ | ----------- | --------------------------------------------------------- |
| `X-DF-Response-Type: step`     | 200-299     | [Step](../step/step#Step)                           |
| -                              | 200-299     | [Step](../step/step#Step)                           |
| n/a                            | 304         | [Step](../step/step#Step)                           |
| `X-DF-Response-Type: : action` | 200-299     | [Action Response Body](action/action-response-body#Action-Response-Body) |
| `X-DF-Response-Type: : exit`   | 200-299     | Exit Response, see below.                                 |
| n/a                            | 400-599     | [Error Response Body](error/error-response-body#Error-Response-Body)   |

### Exit Response

A response is determined to be an Exit when the status code is in the 200-299 range, the `exit` property in the triggering action was set to `true`, or the `X-DF-Response-Type: exit` header is provided.
The body is expected to be a JSON object describing the result value of the flow. The client will merge the `action.result` with the response body and exit the flow with that merged value.

When the triggering action has `exit: true` the `X-DF-Response-Type` header is irrelevant.

| Status Code | Response Type                                           |
| ----------- | --------------------------------------------------------|
| 200-299     | Exit Response, see above.                               |
| 400-599     | [Error Response Body](error/error-response-body#Error-Response-Body) |


