---
id: t3u8b6byi9xi20iz6tbjmco
title: Blazor
desc: ''
updated: 1706852603488
created: 1704416587906
---

```yaml
url: https://dotnet.microsoft.com/en-us/apps/aspnet/web-apps/blazor
alternatives: 
  - [[prdct.React]]
  - [[prdct.vaadin]]
  - [[prdct.flutter]]
related:
  - 
```

## Pros

- wide range of polished component libraries, many of which are free even for commercial use. Consider the offerings from [MudBlazor](https://mudblazor.com/), [MatBlazor](https://www.matblazor.com/), [Radzen](https://razor.radzen.com/), [Ant Design](https://antblazor.com/en-US/components/overview), [Telerik](https://www.telerik.com/blazor-ui), and the [Blazored](https://github.com/Blazored) collectionpho

## Cons

- slow startup: "download an embedded version of the .NET runtime (compiled to WebAssembly), along with DLLs for your application and the .NET class libraries it uses (compiled to Microsoft’s [Common Intermediate Language](https://en.wikipedia.org/wiki/Common_Intermediate_Language), just like every version of .NET since 2000). The download size is a non-negotiable 2 or 3 MB. The startup delay ranges from fractions of a second to several seconds or — occasionally — [even more](https://twitter.com/firstdrafthell/status/1422154020546879490)."
  - caveat: "It Blazor could open the door wider to optimized browser applications, it’s startup lag might not matter so much."
- 