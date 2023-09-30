---
sidebar_label: "Introduction"
sidebar_position: 1
---

# Introduction

Let's try to understand why do we need one more selectors language if we already have XPath and CSS selectors.

## What is wrong with CSS selectors?

CSS selectors are nice. But not powerful.
Two major missing features are:

- Search elements by text
- Search elements with specific inner elements

Search by text is a must have for UI automation. Search by inner elements is very useful when we work with the lists.  
Imagine we have the following component on the page.

```html title="contacts.component.html"
<ul id="contacts">
  <li>
    <span>Rebekah</span>
    <>...</>
    // highlight-start
    <button class="send-button">Send</button>
    // highlight-end
  </li>
  <li>
    <span>Marina</span>
    <>...</>
    <button class="send-button">Send</button>
  </li>
</ul>
```

Lets say that our task is to send message to _Rebekah_. To do that we need to find the corresponding _Send_ button.  
We could easily find all buttons.

```title="CSS"
#contacts .send-button
```

But if we want to find the button for the specific user, CSS selectors will not be able to help.

## What is wrong with XPath?

Let's try to use XPath to solve the previous task.

```title="XPath"
//*[@id='contacts']/descendant::li[descendant::span[text()[normalize-space(.)='Rebekah']]]/descendant::*[contains(@class,'send-button')]
```

This selector will return one element, exactly the one that we want to click.
This is achieved thanks to ability of XPath to search by text and to verify inner elements.  
So, XPath is very poweful. But, it is wordy and not easy to read and understand. It is not adapted for HTML and does not have special sintax for the features we use the most in automated tests like search by ids and classes.

## How could we improve CSS selectors?

What if we could use this kind of sintax to searh by text in CSS selectors

```title="Search by text in XCSS"
li span['Rebekah']
```

And search by inner elements like this

```title="Search by inner element in XCSS"
li[span['Rebekah']]
```

Then our selector for the _Send_ button would be

```title="XCSS selector for Send button"
#contacts li[span['Rebekah']] .send-button
```

The goal of XCSS is to add functionality of XPath to CSS selectors. It does not add any new features compared to XPath, but simplifies creating selectors by making CSS more powerful.
