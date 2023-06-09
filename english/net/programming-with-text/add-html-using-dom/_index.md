---
title: Add HTML Using DOM
linktitle: Add HTML Using DOM
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add HTML content using DOM in Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/programming-with-text/add-html-using-dom/
---

This tutorial will guide you through the process of adding HTML content using DOM (Document Object Model) in Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to add the HTML content, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
```

## Step 3: Set the document directory and output file path
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Create a new Document object
Instantiate a new `Document` object by adding the following line of code:

```csharp
Document doc = new Document();
```

## Step 5: Add a page to the document
Add a new page to the document by using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `page`.

```csharp
Page page = doc.Pages.Add();
```

## Step 6: Create an HtmlFragment with the HTML content
Instantiate an `HtmlFragment` object and provide the desired HTML content. In the provided code, the HTML content is assigned to the variable `titel`. You can modify the HTML content as needed.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Step 7: Set margin information
Adjust the bottom and top margin of the HTML fragment if necessary. In the provided code, the bottom margin is set to 10 and the top margin is set to 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Step 8: Add the HtmlFragment to the page
Add the `HtmlFragment` object to the paragraphs collection of the page.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Step 9: Save the PDF document
Save the PDF document using the `Save` method of the `Document` object. Specify the output file path that you set in Step 3.

```csharp
doc.Save(dataDir);
```

## Step 10: Display the success message
Display a success message along with the path where the PDF file was saved.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Sample source code for Add HTMLUsing DOM using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document object
Document doc = new Document();
// Add a page to pages collection of PDF file
Page page = doc.Pages.Add();
// Instantiate HtmlFragment with HTML contnets
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Set bottom margin information
titel.Margin.Bottom = 10;
// Set top margin information
titel.Margin.Top = 200;
// Add HTML Fragment to paragraphs collection of page
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Save PDF file
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Conclusion
You have successfully added HTML content using DOM in Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.
