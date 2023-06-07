---
title: Rendering Replaceable Symbols
linktitle: Rendering Replaceable Symbols
second_title: Aspose.PDF for .NET API Reference
description: Learn how to render replaceable symbols in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 310
url: /net/programming-with-text/rendering-replaceable-symbols/
---

In this tutorial, we will explain how to render replaceable symbols in a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of creating a PDF, adding a text fragment with newline markers, setting text properties, positioning the text, and saving the PDF using the provided C# source code.

## Prerequisites

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where you want to save the generated PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your desired directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a PDF Document and Page

Next, we create a new PDF document and add a page to it using the `Document` class and `Page` class from the Aspose.PDF library.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Step 3: Add Text Fragment with Newline Markers

We create a `TextFragment` object and set its text to include newline markers (`Environment.NewLine`) to represent multiple lines of text.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Step 4: Set Text Fragment Properties

We can set various properties for the text fragment if desired, such as font size, font, background color, and foreground color.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Step 5: Create Text Paragraph and Position

We create a `TextParagraph` object, append the text fragment to the paragraph, and set the position of the paragraph on the page.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Step 6: Add Text Paragraph to the Page

We create a `TextBuilder` object with the page and append the text paragraph to the text builder.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Step 7: Save the PDF Document

Finally, we save the PDF document to the specified output file.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Sample source code for Rendering Replaceable Symbols using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Initialize new TextFragment with text containing required newline markers
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Set text fragment properties if necessary
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Create TextParagraph object
TextParagraph par = new TextParagraph();
// Add new TextFragment to paragraph
par.AppendLine(textFragment);
// Set paragraph position
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Create TextBuilder object
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Add the TextParagraph using TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, you have learned how to render replaceable symbols in a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can create a PDF, add text with newline markers, set text properties, position the text on the page, and save the PDF.
