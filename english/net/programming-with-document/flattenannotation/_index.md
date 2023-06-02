---
title: Flatten Annotation
linktitle: Flatten Annotation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to flatten annotations in a PDF document using Aspose.PDF for .NET. Preserve annotations and prevent accidental alteration.
type: docs
weight: 150
url: /net/programming-with-document/flattenannotation/
---

Aspose.PDF for .NET is a powerful library that enables developers to work with PDF documents programmatically. One of the features that it provides is the ability to flatten annotations in PDF documents. Flattening annotations in a PDF document means that the annotations become part of the document content and can no longer be edited or deleted. This is useful when you want to ensure that the annotations are preserved and cannot be accidentally altered.

In this tutorial, we will discuss how to use Aspose.PDF for .NET to flatten annotations in a PDF document. We will provide a step-by-step guide on how to do this, along with example source code.

## Step 1: Create a new C# Console Application
To get started, create a new C# Console Application in Visual Studio. You can name it whatever you like. Once the project is created, you need to add a reference to the Aspose.PDF for .NET library.

## Step 2: Import the Aspose.PDF Namespace
Add the following line of code at the top of your C# file to import the Aspose.PDF namespace:

```csharp
using Aspose.Pdf;
```

## Step 3: Open the PDF Document
Open the PDF document that you want to flatten:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Step 4: Flatten the Annotations
Flatten the annotations in the PDF document:

```csharp
foreach (var page in pdfDocument.Pages)
{
    foreach (var annotation in page.Annotations)
    {
        annotation.Flatten();
    }
}
```

## Step 5: Save the Updated Document
Save the updated document:

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

### Example source code for Flatten Annotation using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Flatten annotations
foreach (var page in pdfDocument.Pages)
{
	foreach (var annotation in page.Annotations)
	{
		annotation.Flatten();
	}

}
// Save updated document
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

## Conclusion
In this tutorial, we have discussed how to flatten annotations in a PDF document using Aspose.PDF for .NET. Flattening annotations in a PDF document is a useful feature that ensures that the annotations are preserved and cannot be accidentally altered. Aspose.PDF for .NET provides a simple and easy-to-use API to work with PDF documents, including flattening annotations. 


