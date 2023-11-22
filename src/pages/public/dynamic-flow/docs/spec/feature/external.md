---
title: External
---

# External



External specifies a URL to be opened automatically when a step loads. Url-opening behaviour depends on the platform.
General guidance is as follows:

Web:
- Open a URL in a new browser tab.

Mobile:
- Open a URL in the default browser.
- Or open another app via a universal link.

External is typically used alongside [Polling](polling#Polling).

### Example

```kt
Step.build {
    id = "external example"
    title = ""
    external {
        url = "https://foo.bar/external-request?id=12345"
    }
    layout {
        heading {
            text = "Your bank is opening in another window"
        }
        paragraph {
            text = "Please follow their instructions."
        }
        markdown {
            // Note that the "Reopen window" button/link is just a normal Markdown link that happens to specify the same URL as External.
            content = "[Reopen window](https://foo.bar/external-request?id=12345)"
        }
    }
}
```


## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `url`
* String
* Yes
*
  The URL to open.
{% /table %}
