---
title: Hide Page Numbers In TOC
linktitle: Hide Page Numbers In TOC
second_title: Aspose.PDF for .NET API Reference
description: Learn how to hide page numbers in the Table of Contents using Aspose.PDF for .NET. Follow this detailed guide with code examples to create professional PDFs.
type: docs
weight: 220
url: /net/programming-with-document/hidepagenumbersintoc/
---
## Introduction

When you’re working with PDFs, sometimes you might want to generate a Table of Contents (TOC) but keep things sleek by hiding the page numbers. Maybe the document flows better without them, or perhaps it's an aesthetic choice. Whatever your reason, if you're working with Aspose.PDF for .NET, this tutorial will show you exactly how to hide page numbers in your TOC.

## Prerequisites

Before we get started, there are a few things you'll need in place. Here’s a quick checklist:

- Visual Studio Installed: You’ll need a working version of Visual Studio to code along.
- Aspose.PDF for .NET Library: Make sure you’ve installed the Aspose.PDF for .NET library.
  - Download link: [Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/)
- Temporary License: If you're testing out the features, it's helpful to have a temporary license.
  - Temporary license: [Get it here](https://purchase.aspose.com/temporary-license/)

## Import Packages

Before jumping into the code, ensure you import the following namespaces in your C# project. These will provide the necessary classes and methods for working with PDF documents and creating your Table of Contents (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Now that your environment is ready and packages are imported, let's break down each step of the process. We’ll cover every part of the code to ensure clarity, so you can follow along easily.

## Step 1: Initialize Your PDF Document

The first thing we need to do is create a new PDF document and add a page for the Table of Contents (TOC).


```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: This is the directory where your output file will be saved.
- Document(): Initializes a new PDF document.
- Pages.Add(): Adds a new blank page to the document, which will later hold your TOC.

## Step 2: Set Up TOC Info and Title

Next, we’ll define the TOC information, including setting the title that will appear at the top of the TOC.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: This object holds all the information about the TOC.
- TextFragment: Represents the text of the TOC title, here we set it as "Table Of Contents."
- FontStyle: We style the TOC title by setting its size to 20 and making it bold.
- tocPage.TocInfo: We assign the TOC info to the page that will display the TOC.

## Step 3: Hide Page Numbers in TOC

Now for the fun part! Here’s where we configure the TOC to hide the page numbers.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

- IsShowPageNumbers: This is the magic switch that hides the page numbers. Set it to `false`, and the page numbers won’t appear in the TOC.
- FormatArrayLength: We set this to 4, indicating that we want to define formatting for four levels of TOC headings.

## Step 4: Customize TOC Formatting

To add more style to your TOC, we’ll now define formatting for different levels of headings.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: This array controls the formatting of TOC entries. Each index represents a different heading level.
- Margin and TextStyle: We set margins and apply font styles such as bold, italic, and underline for each heading level.

## Step 5: Add Headings to the Document

Finally, let’s add the actual headings that will be part of the TOC.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Heading and TextSegment: These represent the headings that will appear in your TOC. Each level gets its own heading.
- IsAutoSequence: Automatically numbers the headings.
- IsInList: Ensures that each heading appears in the TOC.

## Step 6: Save the Document

Once everything is set, save the PDF document to your specified output file.

```csharp
doc.Save(outFile);
```

And that's it! You've successfully created a PDF with a Table of Contents, and the page numbers are hidden!

## Conclusion

Creating a Table of Contents in a PDF and hiding page numbers might seem tricky, but with Aspose.PDF for .NET, it's a breeze. By following this step-by-step guide, you’ve learned how to customize the TOC format, hide page numbers, and apply different styles to your headings. Now you can create professional PDFs tailored to your exact needs.

## FAQ's

### Can I show page numbers for specific headings in the TOC?
No, Aspose.PDF hides or shows page numbers for the entire TOC. You can't selectively hide them for specific entries.

### Is it possible to add more levels to the TOC?
Yes, you can increase the `FormatArrayLength` to define more levels of TOC headings.

### How can I change the font for all TOC entries?
You can change the font by modifying the `TextState.Font` property for each level in the `FormatArray`.

### Can I insert hyperlinks in the TOC?
Yes, you can link each TOC entry to a specific section in the document using the `Heading.TocPage` property.

### Do I need a license for Aspose.PDF?
Yes, a valid license is required for production use. You can get a temporary license [here](https://purchase.aspose.com/temporary-license/) to test the features.
