---
sidebar_position: 1
---

# Playwright

Start using XCSS in your Playwright project in just a few simple steps.

## Installation

Install XcssSelectors package to your project.

```bash
dotnet add package XcssSelectors
```

## Add extension method for IPage

```ts
internal static class IPageExtensions
{
    public static ILocator LocatorXcss(this IPage page, string xcssSelector)
    {
        var xcss = XcssSelectors.XCSS.FromXcss(xcssSelector);
        return page.Locator(xcss.Xpath);
    }
}
```

## Start using XCSS in your page object

```ts
internal class ContactsPage
{
    private readonly IPage _page;

    public ContactsPage(IPage page)
    {
        _page = page;
    }

    public async void SendMessageTo(string contact)
    {
        string buttonXcss = $"#contacts li[>span['${contact}']]>.send-button";
        await _page.LocatorXcss(buttonXcss).ClickAsync();
    }
}
```
