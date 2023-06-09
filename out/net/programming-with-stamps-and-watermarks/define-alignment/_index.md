---
title: Define Alignment
linktitle: Define Alignment
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily set text alignment in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 70
url: /content/net/programming-with-stamps-and-watermarks/define-alignment/
---
In this tutorial, we will take you step by step on how to set text alignment in a PDF document using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to create a centered text stamp in the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Loading the PDF document

The first step is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiate a Document object with the input file
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 3: Defining the alignment

Now that you have loaded the PDF document, you can set the alignment of the text stamp. Here's how:

```csharp
// Instantiate a FormattedText object with the example string
FormattedText text = new FormattedText("This");

// Add a new line of text to FormattedText
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// Create a TextStamp object using FormattedText
TextStamp stamp = new TextStamp(text);

// Specify the horizontal alignment of the text buffer as centered
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Specify the vertical alignment of the text buffer as centered
stamp.VerticalAlignment = VerticalAlignment.Center;

// Specify the horizontal alignment of the text in the TextStamp as centered
stamp.TextAlignment = HorizontalAlignment.Center;

// Set top margin for buffer object
stamp. TopMargin = 20;

// Add the stamp object to the first page of the document
doc.Pages[1].AddStamp(stamp);
```

The code above creates a centered text buffer using the FormattedText class to specify the content and sets the horizontal and vertical alignment of the text buffer.

## Step 4: Save the output document

Once you have set the text stamp alignment, you can save the modified PDF document. Here's how:

```csharp
// Save the updated document
doc.Save(dataDir);
```

The above code saves the edited PDF document to the specified directory.

### Sample source code for Define Alignment using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate Document object with input file
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// Instantiate FormattedText object with sample string
FormattedText text = new FormattedText("This");

// Add new text line to FormattedText
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// Create TextStamp object using FormattedText
TextStamp stamp = new TextStamp(text);

// Specify the Horizontal Alignment of text stamp as Center aligned
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Specify the Vertical Alignment of text stamp as Center aligned
stamp.VerticalAlignment = VerticalAlignment.Center;

// Specify the Text Horizontal Alignment of TextStamp as Center aligned
stamp.TextAlignment = HorizontalAlignment.Center;

// Set top margin for stamp object
stamp.TopMargin = 20;

// Add the stamp object over first page of document
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// Save the udpated document
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## Conclusion

Congratulation ! You have learned how to set text alignment in a PDF document using Aspose.PDF for .NET. You can now apply this knowledge to create text stamps with different alignments in your PDF documents.
