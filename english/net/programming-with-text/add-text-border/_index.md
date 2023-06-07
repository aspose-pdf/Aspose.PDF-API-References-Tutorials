---
title: Add Text Border
linktitle: Add Text Border
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a text border to a PDF document using Aspose.PDF for .NET.
type: docs
weight: 70
url: /net/programming-with-text/add-text-border/
---

This tutorial will guide you through the process of adding a text border using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to add the text border, add the following using directive at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Create a new Document object
Instantiate a new `Document` object by adding the following line of code:

```csharp
Document pdfDocument = new Document();
```

## Step 5: Add a page to the document
Add a new page to the document by using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Step 6: Create a TextFragment
Create a `TextFragment` object and provide the desired text. Set the position of the text fragment using the `Position` property. In the provided code, the text is set to "main text" and positioned at (100, 600) on the page.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Step 7: Set text properties
Customize the text properties such as font size, font type, background color, foreground color, etc. In the provided code, properties such as font size, font, background color, foreground color, and stroking color are set for the text fragment.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Step 8: Enable text border
To enable the text border, set the `DrawTextRectangleBorder` property of the text fragment's `TextState` to `true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Step 9: Add the TextFragment to the page
Use the `TextBuilder` class to add the `TextFragment` object to the page.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Step 10: Save the PDF document
Save the PDF document using the `Save` method of the `Document` object. Specify the output file path that you set in Step 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Sample source code for Add Text Border using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create new document object 
Document pdfDocument = new Document();
// Get particular page
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Create text fragment
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Set text properties
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Set StrokingColor property for drawing border (stroking) around text rectangle
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Set DrawTextRectangleBorder property value to true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Save the document
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusion
You have successfully added a text border to your PDF document using Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.
