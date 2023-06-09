---
title: Extract Text Using Text Device
linktitle: Extract Text Using Text Device
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract text from a PDF document using the Text Device in Aspose.PDF for .NET.
type: docs
weight: 210
url: /content/net/programming-with-text/extract-text-using-text-device/
---

This tutorial will guide you through the process of extracting text from a PDF document using the Text Device in Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to extract text, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Open the PDF document
Open an existing PDF document using the `Document` constructor and passing the path to the input PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Step 5: Extract text using Text Device
Create a `StringBuilder` object to hold the extracted text. Iterate through each page of the document and use a `TextDevice` to extract the text from each page.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Step 6: Save the extracted text
Specify the output file path and save the extracted text to a text file using the `File.WriteAllText` method.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Sample source code for Extract Text Using Text Device using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
// String to hold extracted text
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Create text device
		TextDevice textDevice = new TextDevice();
		// Set text extraction options - set text extraction mode (Raw or Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Convert a particular page and save text to the stream
		textDevice.Process(pdfPage, textStream);
		// Convert a particular page and save text to the stream
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Close memory stream
		textStream.Close();
		// Get text from memory stream
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Save the extracted text in text file
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusion
You have successfully extracted text from a PDF document using the Text Device in Aspose.PDF for .NET. The extracted text has been saved to the specified output file.