---
title: Search Result
---

# Search Result



Represents a single entry in a [Search Response Body](search-response-body#Search-Response-Body).

## Subtypes

### Action



A search result which contains an [Action](../../feature/action#Action) to perform when the result is selected.

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `description`
* String
* No
*
  The user-facing description.
---
* `icon`
* [Icon](../../misc/icon#Icon)
* No
*
  An icon representing the result.
---
* `image`
* [ImageLayout](../../layout/image-layout#Image-Layout)
* No
*
  An image representing the result.
---
* `title`
* String
* Yes
*
  The user-facing title.
---
* `type`
* [SearchResult.Type](search-result#Type)
* Yes
*
  It must be `action`.
---
* `value`
* [Action](../../feature/action#Action)
* Yes
*
  The action to perform when the option is selected.
{% /table %}
### Search



A search result which contains another search to be performed when selected. Can be used to provide groups of
results or simple pagination.

#### Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `description`
* String
* No
*
  The user-facing description.
---
* `icon`
* [Icon](../../misc/icon#Icon)
* No
*
  An icon representing the result.
---
* `image`
* [ImageLayout](../../layout/image-layout#Image-Layout)
* No
*
  An image representing the result.
---
* `title`
* String
* Yes
*
  The user-facing title.
---
* `type`
* [SearchResult.Type](search-result#Type)
* Yes
*
  It must be `search`.
---
* `value`
* [SearchResult.Search.SearchRequest](search-result#Search-Request)
* Yes
*
  A search configuration to used when the option is selected.
{% /table %}
## Related Types

### Type



The possible types of search results.

#### Values

| Value | Description |
| ---| --- |
| `action` | A result containing an action. |
| `search` | A result containing another search to perform. |

### Search Request



A search request.

#### Properties

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
  The HTTP method to use for the request.
---
* `param`
* String
* Yes
*
  The name of the parameter to place the search term under. If the HTTP method allows a request body this will be the property name to use in the request body JSON object. If the HTTP method does not allow a request body, this will be included as a query parameter.
---
* `query`
* String
* Yes
*
  The value of the query.
---
* `url`
* String
* Yes
*
  The URL for the request. Either absolute or relative to the base URL of the flow.
{% /table %}
