---
title: Add Subsequent Lines Indent
linktitle: Add Subsequent Lines Indent
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add subsequent lines indent to text using Aspose.PDF for .NET.
type: docs
weight: 60
url: /content/net/programming-with-text/add-subsequent-lines-indent/
---

This tutorial will guide you through the process of adding subsequent lines indent to text using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to add subsequent lines indent, add the following using directive at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Create a new Document object
Instantiate a new `Document` object by adding the following line of code:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Step 5: Add a page to the document
Add a new page to the document by using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Step 6: Create a TextFragment with subsequent lines indent
Instantiate a `TextFragment` object and provide the desired text. In the provided code, the text is assigned to the variable `text`. Then, initialize `TextFormattingOptions` for the `TextFragment` and specify the `SubsequentLinesIndent` value.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Step 7: Add the TextFragment to the page
Add the `TextFragment` object to the paragraphs collection of the page.

```csharp
page.Paragraphs.Add(text);
```

## Step 8: Repeat steps 6 and 7 for additional lines
To add subsequent lines with the same indent, repeat steps 6 and 7 for each line. Update the text content as needed.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Step 9: Save the PDF document
Save the PDF document using the `Save` method of the `Document` object. Specify the output file path.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Sample source code for Add Subsequent Lines Indent using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create new document object 
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Initilize TextFormattingOptions for the text fragment and specify SubsequentLinesIndent value
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusion
You have successfully added subsequent lines indent to text using Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.