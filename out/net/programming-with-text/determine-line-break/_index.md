---
title: Determine Line Break
linktitle: Determine Line Break
second_title: Aspose.PDF for .NET API Reference
description: Learn how to determine line breaks in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 130
url: /content/net/programming-with-text/determine-line-break/
---

This tutorial will guide you through the process of determining line breaks in a PDF document using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to determine line breaks, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Create a new Document instance
Instantiate a new `Document` object by adding the following line of code:

```csharp
Document doc = new Document();
```

## Step 5: Add a page to the document
Add a new page to the document using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `page`.

```csharp
Page page = doc.Pages.Add();
```

## Step 6: Add text fragments with line breaks
Create a loop to add multiple text fragments to the page, each containing a paragraph with line breaks.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Step 7: Save the PDF document and extract line break information
Save the PDF document using the `Save` method of the `Document` object. Then, extract the line break information using the `GetNotifications` method of the desired page.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

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

## Conclusion
You have successfully determined line breaks in a PDF document using Aspose.PDF for .NET. The line break information has been extracted and saved to a text file.