---
title: Determine Line Break
linktitle: Determine Line Break
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 130
url: /net/programming-with-text/determine-line-break/
---
### Sample source code for Determine Line Break using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            Page page = doc.Pages.Add();
            for (int i = 0; i < 4; i++)
            {
                TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
                text.TextState.FontSize = 20;
                page.Paragraphs.Add(text);
            }
            doc.Save(dataDir + "DetermineLineBreak_out.pdf");
            string notifications = doc.Pages[1].GetNotifications();
            File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```