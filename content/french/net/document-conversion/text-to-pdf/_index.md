---
title: Text To PDF
linktitle: Text To PDF
second_title: Aspose.PDF for .NET API Reference
description: Simple and efficient conversion of text files to PDF using Aspose.PDF for .NET.
type: docs
weight: 300
url: /fr/net/document-conversion/text-to-pdf/
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

### FAQ's

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that enables developers to work with PDF documents in C# applications. It offers various functionalities, including converting plain text to PDF.

#### Q: Why would I want to convert a text file to a PDF?

A: Converting text files to PDF format allows for better document management, sharing, and distribution. PDF files offer consistent formatting across different devices and operating systems.

#### Q: How can I load a text file and convert it to a PDF using Aspose.PDF for .NET?

A: To load a text file, you can use the `StreamReader` class to read the contents of the file. Then, create a `Document` object to represent the PDF document. Add a new page and a `TextFragment` containing the text from the text file. Finally, save the resulting PDF using the `Save` method of the `Document` object.

#### Q: Can I customize the appearance of the text in the PDF?

A: Yes, Aspose.PDF for .NET provides various options to customize the appearance of text in the resulting PDF, such as font style, size, color, and alignment.

#### Q: Is the text formatting preserved in the resulting PDF?

A: Yes, Aspose.PDF for .NET preserves the text formatting and layout during the text to PDF conversion, ensuring accurate representation of the original content.