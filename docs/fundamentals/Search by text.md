---
sidebar_label: "Search by text"
sidebar_position: 3
---

| XCSS               | XPath                                                    |
| ------------------ | -------------------------------------------------------- |
| `span['Rebekah']`  | `//span[text()[normalize-space(.)='Rebekah']]`           |
| `span[~'Rebekah']` | `//span[text()[contains(normalize-space(.),'Rebekah')]]` |
