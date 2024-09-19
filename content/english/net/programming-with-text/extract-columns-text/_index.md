---
title: Extract Columns Text In PDF File
linktitle: Extract Columns Text In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract columns of text from PDF files using Aspose.PDF for .NET. This guide breaks down each step with code examples and explanations.
type: docs
weight: 150
url: /net/programming-with-text/extract-columns-text/
---
## Introduction

Are you working with PDF files and need to extract text in a specific column format? Whether you’re processing invoices, reports, or any structured documents, extracting text accurately from a PDF can be a tricky business. This is where Aspose.PDF for .NET steps in to simplify the process. In this tutorial, we’ll walk you through how to extract columns of text from a PDF file with ease. 

## Prerequisites

Before diving into the code, let's cover the essential things you'll need:

- Aspose.PDF for .NET: Ensure you have the latest version of Aspose.PDF for .NET installed. If not, you can [download it here](https://releases.aspose.com/pdf/net/).
- Development Environment: You’ll need Visual Studio or another .NET development environment to work with the code.
- PDF Document: Have a sample PDF document on hand, preferably one with columns of text, as we will be extracting text from it.

If you haven’t installed Aspose.PDF for .NET yet, you can grab a [free trial](https://releases.aspose.com/) or [buy a license](https://purchase.aspose.com/buy) for full features. You can also apply for a [temporary license](https://purchase.aspose.com/temporary-license) if needed.

## Import Namespaces

To use Aspose.PDF for .NET in your project, you’ll need to import the following namespaces:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Step-by-Step Guide: Extract Columns of Text from a PDF

Now, let's break down each part of the code to better understand how it works. Follow along as we go step by step, explaining each segment of the process.

## Step 1: Load the PDF Document

The first thing you need to do is load your PDF file into the `Document` object. This is how Aspose.PDF interacts with your document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

In this step, we’re simply defining the directory where your PDF document is stored. Replace `"YOUR DOCUMENT DIRECTORY"` with the path to your local PDF file. The `Document` object loads the PDF into memory, making it accessible for further processing.

## Step 2: Set Up the Text Fragment Absorber

Next, we’ll use a `TextFragmentAbsorber` to absorb or capture all the text from the PDF file. This absorber class is designed to extract text fragments from specific areas in your PDF, which makes it ideal for extracting columns of text.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Here, we create an instance of `TextFragmentAbsorber` and apply it to all pages of the PDF using `Accept()`. The `TextFragmentCollection` stores the extracted text, and from this collection, we can manipulate or extract text as needed.

## Step 3: Adjust the Font Size of the Extracted Text

Once you’ve captured the text fragments, you might want to reduce their font size, especially when the original text is too large. In this example, we’re reducing the font size by 70%.

```csharp
foreach (TextFragment tf in tfc)
{
    // Reduce font size by 70%
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

This code loops through each `TextFragment` in the collection and reduces its font size by 70%. Adjusting the font size can make the extracted text easier to manage, especially if you're formatting it for different purposes.

## Step 4: Save the Document to a Memory Stream

After modifying the text, we save the PDF into a `MemoryStream`. This allows us to keep the document in memory for further processing without needing to write it back to the disk.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Here, we save the PDF into a memory stream and then reload the document. This method is useful when you’re working with large files and want to avoid unnecessary disk operations.

## Step 5: Extract All Text Using Text Absorber

Now that we’ve prepared the PDF, it’s time to extract the text. We’ll use `TextAbsorber` to grab all the text from the document.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

In this step, the `TextAbsorber` absorbs all the text from the PDF, and the extracted text is stored in the `extractedText` string. This is where the magic happens—your columns of text are now in plain-text format!

## Step 6: Save the Extracted Text to a File

Finally, we save the extracted text into a `.txt` file for easy access and further use.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

This code writes the extracted text into a new `.txt` file and saves it in your specified directory. A message is displayed in the console to confirm that the process was successful.

## Conclusion

There you have it! Extracting columns of text from a PDF file using Aspose.PDF for .NET is easier than you might think. With just a few lines of code, you can load a PDF, extract specific text, adjust formatting, and save the results into a text file.

This technique is incredibly useful for processing structured documents like tables, reports, or any content organized in columns. Whether you need to automate data extraction or process bulk documents, Aspose.PDF provides the tools to make it happen efficiently.

## FAQ's

### Can I extract text from specific pages of a PDF?  
Yes! You can modify the `TextFragmentAbsorber` to target specific pages using the `pdfDocument.Pages[pageIndex].Accept(tfa);` method.

### Is it possible to extract text from only one column in a multi-column PDF?  
Yes, but you’ll need to work with the coordinates of the text fragments using `TextFragment.Rectangle` to target specific areas of the document.

### How can I improve the accuracy of text extraction?  
For better accuracy, ensure the PDF’s structure is well-defined and avoid documents with complex layouts. You can also fine-tune the `TextFragmentAbsorber` to extract text based on font styles, sizes, or regions.

### Does Aspose.PDF support text extraction from scanned documents?  
Yes, but you’ll need to use OCR (Optical Character Recognition) technology. Aspose provides tools for this as well.

### How do I handle large PDF files with thousands of pages?  
For large PDFs, process the document in chunks by extracting text from a few pages at a time to avoid high memory usage.
