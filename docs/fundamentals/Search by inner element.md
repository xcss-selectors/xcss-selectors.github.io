---
sidebar_label: "Search by inner elements"
sidebar_position: 4
---

| XCSS                 | XPath                                                  |
| -------------------- | ------------------------------------------------------ |
| `li[.send-message]`  | `//li[descendant::*[contains(@class,'send-message')]]` |
| `li[>.send-message]` | `//li[*[contains(@class,'send-message')]]`             |

:::caution

There is one exception when identificator inside the brackets is treated as attribute instead of the tag.

`input[my-attribute]` will be converted to `//input[@my-attribute]`, instead of `//input[descentdant::my-attribute]`.  
But if we add other constraints explicitly showing that it is a tag, it will be treated as a tag.  
`div[my-component[1]]` will be converted to `//div[descendant::my-component[1]]`

:::
