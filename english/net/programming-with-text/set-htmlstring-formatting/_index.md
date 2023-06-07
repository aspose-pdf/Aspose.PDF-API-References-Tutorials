---
title: Set HTMLString Formatting
linktitle: Set HTMLString Formatting
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 490
url: /net/programming-with-text/set-htmlstring-formatting/
---
### Sample source code for Set HTMLString Formatting using Aspose.PDF for .NET 
```csharp
            HtmlFragment html = new HtmlFragment("some text");
            html.TextState = new TextState();
            html.TextState.Font = FontRepository.FindFont("Calibri");
```