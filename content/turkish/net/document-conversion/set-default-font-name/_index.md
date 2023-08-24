---
title: Set Default Font Name
linktitle: Set Default Font Name
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to set default font name in PDF file using Aspose.PDF for .NET.
type: docs
weight: 270
url: /tr/net/document-conversion/set-default-font-name/
---
In this tutorial, we will show you how to set the default font name in a PDF file using Aspose.PDF for .NET. Sometimes when you extract images from a PDF file, you may encounter missing font issues. By specifying a default font name, you can ensure that extracted text will be displayed correctly. Follow the steps below to set the default font name in a PDF file.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading the PDF document
The first step is to load the PDF document into a `Document` object. Use the following code:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Code to add
}
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Set default font name
Next, we'll set the default font name using the `DefaultFontName` option of the `RenderingOptions` object. Use the following code:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Code to add
     }
}
```

Be sure to replace `"Arial"` with the desired font name.

## Step 3: Image Extraction
Next, we will extract the image from the specified page of the PDF document. Use the following code:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

Be sure to specify the correct page number in `pdfDocument.Pages[1]`.

### Example source code for Set Default Font Name using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Conclusion
In this tutorial, we learned how to set the default font name in a PDF file using Aspose.PDF for .NET. By specifying a default font name, you can ensure that extracted text will be displayed correctly. Use this method to resolve missing font issues when extracting images from PDF files.

### FAQ's

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that enables developers to work with PDF documents in C# applications. It offers various functionalities, including setting the default font name in a PDF file.

#### Q: Why would I need to set the default font name in a PDF file?

A: Setting the default font name is useful when extracting text from a PDF document. If the PDF contains text with fonts that are not available on the extraction machine, specifying a default font name ensures correct text display.

#### Q: How can I load a PDF document and set the default font name using Aspose.PDF for .NET?

A: To load a PDF document and set the default font name, you can use the `Document` class to load the PDF file and the `RenderingOptions.DefaultFontName` property to specify the desired default font name.

#### Q: Can I choose any font as the default font name?

A:Yes, you can choose any font that is available on the extraction machine as the default font name. Use a font that closely matches the missing fonts in the original PDF to ensure accurate text rendering.

#### Q: Is setting the default font name a permanent change to the PDF file?

A: No, setting the default font name using Aspose.PDF for .NET is a temporary change made during text extraction. It does not modify the original PDF file.