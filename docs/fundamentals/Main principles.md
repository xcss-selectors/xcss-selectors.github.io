---
sidebar_label: "Main principles"
sidebar_position: 1
---

## Conversion to XPath

XCSS format is designed to eliminate the gap between CSS and XPath.
XCSS is CSS-like selectors format that provides features of XPath.

Under the hood XCSS selectors are transpiled to XPath, so there are two important conclusions from this.

- Any valid XPath is a valid XCSS selector
- Not all CSS selectors features are supported by XCSS selectors, since not all CSS selector features can be converted to XPath

# Any valid XPath is a valid XCSS selector

XCSS is a CSS-like format. But since it is transpiled to XPath under the hood, any XPath selector can also be used in place of XCSS selector.

```ts
findByXcss("//button[text()='Send message']").Click();
```

# Not any CSS selector is a valid XCSS selector

XCSS is a CSS-like format. But not all CSS features can be transpiled to XPath, so XCSS format only supports subset of CSS features, but not all of them.s

```ts
// INVALID: nth-of-type() is not supported in XCSS
findByXcss("button:nth-of-type(2)").Click(); // error
```

# List of CSS selector features supported in XCSS

- Search by id `#contacts`
- Search by class `.send-button`
- Search by attribute `button[class='send-button']`

# List of XPath features supported in XCSS

- Search by text `span['Rebekah']`
- Search by index `li[2]`
- Search by inner element `li[>span['Rebekah']]`
- Search by XPath condition `#contacts li[position() mod 2 = 1]`
