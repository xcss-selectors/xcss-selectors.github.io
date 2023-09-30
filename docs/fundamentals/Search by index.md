---
sidebar_label: "Search by index"
sidebar_position: 2
---

| XCSS              | XPath                                   |
| ----------------- | --------------------------------------- |
| `#contacts li[1]` | `//*[@id='contacts']/descendant::li[1]` |

:::caution

Do not confuse search by index with :nth-child(n) function in CSS.

`#contacts li:nth-child(1)` is equivalent to `#contacts>li[1]`, but not equivalend to `#contacts li[1]`.

:::
