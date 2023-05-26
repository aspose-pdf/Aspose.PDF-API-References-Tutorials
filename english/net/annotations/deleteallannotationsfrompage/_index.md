---
title: Delete All Annotations From Page
linktitle: Delete All Annotations From Page
second_title: Aspose.PDF for .NET API Reference
description: Learn how to delete all annotations from a PDF page with Aspose.PDF for .NET using this step-by-step guide.
type: docs
weight: 40
url: /net/annotations/deleteallannotationsfrompage/
---
Aspose.PDF for .NET is a powerful library that allows developers to create, manipulate, and transform PDF files. In this article, we will explore how to use Aspose.PDF for .NET to delete all annotations from a specific page of a PDF document. We will provide a step-by-step guide to help you understand the process.

Follow the below steps for Delete All Annotations From Page Using Aspose.PDF for .NET

## Step 1: Install Aspose.PDF for .NET

To use Aspose.PDF for .NET, you need to install the library first. You can [download](https://releases.aspose.com/pdf/net/) the library from the Aspose releases and install it on your computer. After installation, you need to add a reference to the library in your project.

## Step 2: Create a New Console Application

Create a new console application in Visual Studio and add a reference to the Aspose.PDF library. In this tutorial, we will use C# language.

## Step 3: Load the PDF Document

In the source code provided, the first thing we do is specify the path to the PDF document. You need to replace "YOUR DOCUMENT DIRECTORY" with the actual path to the PDF document on your computer. Then, we create a new instance of the Document class and load the PDF document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "DeleteAllAnnotationsFromPage.pdf");
```

## Step 4: Delete All Annotations from a Page

To delete all annotations from a specific page of the PDF document, we need to access the Annotations collection of the Page object and call the Delete() method. In the source code provided, we delete all annotations from the second page (index 1) of the PDF document.

```csharp
pdfDocument.Pages[1].Annotations.Delete();
```

## Step 5: Save the Updated PDF Document

After deleting the annotations, we need to save the updated PDF document. In the source code provided, we specify the path to the output PDF document and call the Save() method.

```csharp
dataDir = dataDir + "DeleteAllAnnotationsFromPage_out.pdf";
pdfDocument.Save(dataDir);
```

## Conclusion

In this article, we have provided a step-by-step guide to help you understand how to delete all annotations from a specific page of a PDF document using Aspose.PDF for .NET. By following the steps outlined in this guide, you can easily implement this feature in your own project.

### Example Source Code for Delete All Annotations From Page Using Aspose.PDF for .NET

```csharp
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Open document
	Document pdfDocument = new Document(dataDir + "DeleteAllAnnotationsFromPage.pdf");

	// Delete particular annotation
	pdfDocument.Pages[1].Annotations.Delete();

	dataDir = dataDir + "DeleteAllAnnotationsFromPage_out.pdf";
	// Save updated document
	pdfDocument.Save(dataDir);
``` 

