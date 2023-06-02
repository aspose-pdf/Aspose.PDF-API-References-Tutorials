---
title: Get All Annotations From Page
linktitle: Get All Annotations From Page
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to retrieve all annotations from a PDF page with this step-by-step guide.
type: docs
weight: 70
url: /content/net/annotations/getallannotationsfrompage/
---
This article will guide you through the process of extracting all annotations from a PDF page using Aspose.PDF for .NET. Aspose.PDF for .NET is a library that allows developers to create, edit, and convert PDF documents. With the help of this guide, you will be able to get all the annotations from a specific PDF page using the provided C# source code.

Follow the below steps how to get all Annotations for a PDF page using Aspose.PDF for .NET:

## Step 1: The Path to the Documents Directory

The first step in getting all annotations from a PDF page using Aspose.PDF for .NET is to set the path to the documents directory where your PDF files are stored. You can do this by modifying the following line of code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## Step 2: Your PDF files are stored

Replace "YOUR DOCUMENT DIRECTORY" with the path to the folder where your PDF files are stored. For example:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## Step 3: Open Document

The next step is to open the PDF document that contains the annotations you want to extract. You can do this by adding the following code:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

This line of code initializes a new instance of the Document class and loads the PDF document "GetAllAnnotationsFromPage.pdf". Replace this filename with the name of your PDF file.

## Step 4: Loop through All Annotations

Once you have opened the PDF document, you can loop through all the annotations on a specific page. For example, to loop through all the annotations on the first page of the PDF document, add the following code:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Code goes here
}
```

This code loops through all the annotations on the first page of the PDF document and assigns each annotation to the "annotation" variable.

## Step 5: Get Annotation Properties

To extract the properties of each annotation, you can add the following code inside the foreach loop:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

This code writes the Title, Subject, and Contents of each annotation to the console.

### Example Source Code for Get All Annotations From Page using Aspose.PDF for .NET

Here is the complete source code for getting all annotations from a PDF page using Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Loop through all the annotations
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Get annotation properties
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```
