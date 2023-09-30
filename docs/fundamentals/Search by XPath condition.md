---
sidebar_label: "Search by XPath condition"
sidebar_position: 5
---

We can put any XPath condition inside the brackets and it will be used in resulting XPath as is.

| XCSS                   | XPath                    |
| ---------------------- | ------------------------ |
| `button[last()]`       | `//button[last()]`       |
| `span[not(a)]`         | `//span[not(a)]`         |
| `span[position() > 1]` | `//span[position() > 1]` |
