---
title: Image Layout
---

# Image Layout



Images fetched from URLs.

## Properties

{% table %}
* Property
* Type
* Required
* Description
---
* `accessibilityDescription`
* String
* No
*
  A description of the content of the image to be used by screen readers.
---
* `control`
* String
* No
*
  Specify a particular control to use to represent the layout. If the control is unknown, it will be ignored.
---
* `margin`
* [Size](../misc/size#Size)
* No
*
  The vertical margin to apply above this component. Defaults to `md`.
---
* `size`
* [Size](../misc/size#Size)
* No
*
  The horizontal size of the image. Defaults to `md`. The image is scaled down to fit the provided size while preserving the aspect ratio, and it is never stretched beyond its pixel size. If `xl` is used, the image will fill as much space as it can.
---
* `type`
* String
* Yes
*
  It must be `image`.
---
* `url`
* String
* Yes
*
  The URL to use to fetch the image.
{% /table %}
