---
title: Search Layout
---

# Search Layout



Displays a search input field, which performs a search and returns a [Search Result](../responses/search/search-result#Search-Result).

Results are actions or further searches.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `control`
* String
* No
*
  Specify a particular control to use to represent the layout. If the control is unknown, it will be ignored.
---
* `emptyMessage`
* String
* No
*
  A markdown message which the client should display if the results array is empty.
---
* `margin`
* [Size](../misc/size#Size)
* No
*
  The vertical margin to apply above this component. Defaults to `md`.
---
* `method`
* String
* Yes
*
  The HTTP method to use for the request.
---
* `param`
* String
* Yes
*
  The name of the parameter to place the search term under. If the method is GET, this will be included as a query parameter, otherwise, this will be a property of the JSON object in the request body.
---
* `title`
* String
* Yes
*
  A title to be displayed as a label for the search field.
---
* `type`
* String
* Yes
*
  It must be `search`.
---
* `url`
* String
* Yes
*
  The URL for the request. Either absolute or relative to the base URL of the flow.
{% /table %}
