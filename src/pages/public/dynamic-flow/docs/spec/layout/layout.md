---
title: Layout
---

# Layout



Layouts allow you to display information to the user and customise how a step is structured.

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
* `margin`
* [Size](../misc/size#Size)
* No
*
  The vertical margin to apply above this component. Defaults to `md`.
---
* `type`
* String
* Yes
*
{% /table %}
## Subtypes

| Type | Description |
| --- | --- |
| [Alert Layout](alert-layout#Alert-Layout) | Show an attention-grabbing message. |
| [Box Layout](box-layout#Box-Layout) | A container for a group of components with an optional border. |
| [Button Layout](button-layout#Button-Layout) | A component which performs an [Action](../feature/action#Action) when pressed. |
| [Columns Layout](columns-layout#Columns-Layout) | Allows content to be displayed in two columns. |
| [Decision Layout](decision-layout#Decision-Layout) | A set of options which each perform an [Action](../feature/action#Action). |
| [Form Layout](form-layout#Form-Layout) | Embed a schema inside the layout's structure. |
| [Heading Layout](heading-layout#Heading-Layout) | A heading which can be used to title or separate sections of a layout. |
| [Image Layout](image-layout#Image-Layout) | Images fetched from URLs. |
| [Instructions Layout](instructions-layout#Instructions-Layout) | A list of fields used to inform the user of actions to do and not do. |
| [Loading Indicator Layout](loading-indicator-layout#Loading-Indicator-Layout) | A symbol indicating an indeterminate loading or pending state, when the user should wait for something to happen. |
| [Markdown Layout](markdown-layout#Markdown-Layout) | A block of markdown content. |
| [Paragraph Layout](paragraph-layout#Paragraph-Layout) | A block of plain text. For richer formatting and layout options consider using [Markdown Layout](markdown-layout#Markdown-Layout). |
| [Review Layout](review-layout#Review-Layout) | A list of read-only fields used to show information to the user for review. |
| [Search Layout](search-layout#Search-Layout) | Displays a search input field, which performs a search and returns a [Search Result](../responses/search/search-result#Search-Result). |
| [Status List Layout](status-list-layout#Status-List-Layout) | A list of items with statuses. |

