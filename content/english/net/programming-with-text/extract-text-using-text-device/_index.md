---
title: Extract Text Using Text Device
linktitle: Extract Text Using Text Device
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract text from a PDF document using the Text Device in Aspose.PDF for .NET.
type: docs
weight: 210
url: /net/programming-with-text/extract-text-using-text-device/
---
## Introduction

Extracting text from a PDF can be tricky, especially when dealing with documents that have various formats, embedded fonts, or complex layouts. But with Aspose.PDF for .NET, this process becomes a breeze! Whether you want to convert pages of a PDF into plain text for further analysis or simply need to extract specific sections, Aspose.PDF has you covered. In this tutorial, we'll break down step-by-step how to extract text from a PDF using the TextDevice class in Aspose.PDF. We’ll also provide clear explanations, so you can apply the same methods to your own projects with ease.

## Prerequisites

Before we jump into the code, make sure you have everything in place to follow along. Here’s what you’ll need:

1. Aspose.PDF for .NET: Download the latest version from the [Aspose.PDF for .NET download page](https://releases.aspose.com/pdf/net/).
2. Development Environment: Visual Studio or any other C# development environment.
3. .NET Framework: Ensure that your project is targeting .NET Framework 4.x or higher.
4. Input PDF File: A PDF file that you’ll use for text extraction. Place this in a directory on your machine (we’ll refer to this as `YOUR DOCUMENT DIRECTORY`).

## Import Packages

At the top of your code, you'll need to import the necessary namespaces to work with Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Step 1: Load Your PDF Document

Before extracting text, we need to load the PDF document into memory. In this step, you'll open your PDF using Aspose.PDF's `Document` class. This will allow you to access all pages and content within the file.

```csharp
// Define the path to your PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load the PDF document
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Here, we're using `Document pdfDocument = new Document(dataDir + "input.pdf");` to load the PDF. The `dataDir` variable holds the directory path of your PDF file. This will give us access to the entire document, allowing us to loop through pages and extract content.

## Step 2: Set Up a String Builder for Text Storage

Now that the document is loaded, we need a way to store the extracted text. For this, we’ll use a `StringBuilder` which allows efficient string concatenation.

```csharp
// StringBuilder to hold the extracted text
StringBuilder builder = new StringBuilder();
```

We initialize a `StringBuilder` instance, which will collect text extracted from each page. It’s a more efficient way to handle large strings compared to regular string concatenation in a loop.

## Step 3: Loop Through PDF Pages

Next, we loop through each page of the PDF document to extract the text. We’ll process each page individually using the `TextDevice` class, which is responsible for converting the PDF content to text format.

```csharp
// Loop through all the pages in the PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Process each page for text extraction
}
```

This loop goes through every page of the PDF (`pdfDocument.Pages`). For each page, we will extract the text and add it to our `StringBuilder`.

## Step 4: Extract Text from Each Page

Now, we set up the text extraction process for each page. Here, we’ll create a `TextDevice` object and use it to process the PDF pages. The `TextDevice` extracts raw or formatted text based on the extraction options we set.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Create a text device for text extraction
    TextDevice textDevice = new TextDevice();
    
    // Set text extraction options to 'Pure' mode
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    // Extract text from the current page and save it to the memory stream
    textDevice.Process(pdfPage, textStream);

    // Convert memory stream to text
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Append the extracted text to the StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();`: The `TextDevice` class is used to extract text from the PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);`: This option extracts the raw text without retaining any formatting like fonts or positions. You can also use `TextFormattingMode.Raw` if you need more control over the formatting.
- `textDevice.Process(pdfPage, textStream);`: This processes each page of the PDF and stores the extracted text in a `MemoryStream`.
- Finally, we convert the text from the `MemoryStream` to a string and append it to the `StringBuilder`.

## Step 5: Save Extracted Text to a File

After processing all the pages, the text is stored in the `StringBuilder`. The last step is to save this extracted text to a file.

```csharp
// Define the output path for the text file
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Save the extracted text to a file
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());`: This writes the entire content of the `StringBuilder` into a text file.
- The path for the output file is set by appending a filename (`"input_Text_Extracted_out.txt"`) to the `dataDir` path.

## Conclusion

Extracting text from a PDF using Aspose.PDF for .NET is a simple and efficient process. By following the steps outlined in this guide, you can easily open PDF documents, loop through pages, and extract text into a text file. This is especially useful for processing large volumes of PDF data, performing text analysis, or converting documents for further manipulation.

With Aspose.PDF, you're not limited to text extraction—you can handle annotations, manipulate images, or even convert PDFs into other formats like HTML or Word. The flexibility and power of this library make it an invaluable tool for PDF management in .NET applications.

## FAQ's

### Can Aspose.PDF extract text from image-based PDFs?
No, Aspose.PDF is designed to extract text from content-based PDFs. For image-based PDFs, OCR technology is needed.

### Does Aspose.PDF retain formatting when extracting text?
By default, the text is extracted without formatting, but you can adjust extraction options if you want to keep some formatting.

### Can I extract text from a specific page range?
Yes, you can modify the code to loop over a specific range of pages instead of all pages.

### What are the text extraction modes in Aspose.PDF?
Aspose.PDF provides two modes: Raw and Pure. Raw mode tries to retain the original layout, while Pure mode extracts only the text without formatting.

### Is Aspose.PDF for .NET compatible with .NET Core?
Yes, Aspose.PDF for .NET is fully compatible with .NET Core and .NET Framework.
