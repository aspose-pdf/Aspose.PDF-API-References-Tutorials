---
title: Text to PDF
linktitle: Text to PDF
second_title: Aspose.PDF for .NET API Reference
description: Simple and efficient conversion of text files to PDF using Aspose.PDF for .NET.
type: docs
weight: 300
url: /net/document-conversion/text-to-pdf/
---

This tutorial will walk you through the steps to convert a text file to a PDF file using Aspose.PDF for .NET. Aspose.PDF offers a simple and effective solution for converting plain text to PDF while preserving text formatting and presentation. Follow the steps below to perform this conversion.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Reading the text file
The first step is to read the contents of the text file using the `StreamReader` class. Use the following code:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Read the text file
TextReader tr = new StreamReader(dataDir + "log.txt");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your text file is located.

## Step 2: Creating the PDF document
The second step is to create a `Document` object which will represent the final PDF document. Use the following code:

```csharp
// Create a Document object
Document doc = new Document();
```

## Step 3: Add text to document
The third step is to add the read text to the page of the PDF document. Use the following code:

```csharp
// Add a new page to the document
Page page = doc.Pages.Add();

// Create a TextFragment object and pass the read text as an argument
TextFragment text = new TextFragment(tr.ReadToEnd());

// Add the text paragraph to the page
page.Paragraphs.Add(text);
```

## Step 4: Saving the PDF file
Finally, save the resulting PDF file by specifying the desired path and file name. Use the following code:

```csharp
// Save the resulting PDF file
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Be sure to specify the desired path and filename for the resulting PDF file.

### Example source code for Text to PDF using Aspose.PDF for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Read the source text file
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Instantiate a Document object by calling its empty constructor
	Document doc = new Document();

	// Add a new page in Pages collection of Document
	Page page = doc.Pages.Add();

	// Create an instance of TextFragmet and pass the text from reader object to its constructor as argument
	TextFragment text = new TextFragment(tr.ReadToEnd());
	// Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Add a new text paragraph in paragraphs collection and pass the TextFragment object
	page.Paragraphs.Add(text);

	// Save resultant PDF file
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
In this tutorial, we learned how to convert a text file to a PDF file using Aspose.PDF for .NET. By following the steps given above, you can easily perform this conversion. Use this method to convert your text files to PDF and enjoy the flexibility and quality of Aspose.PDF.
