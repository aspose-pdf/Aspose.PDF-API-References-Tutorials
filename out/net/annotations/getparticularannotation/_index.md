---
title: Get Particular Annotation
linktitle: Get Particular Annotation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to get particular annotation in a PDF document with this step-by-step guide. 
type: docs
weight: 80
url: /content/net/annotations/getparticularannotation/
---
If you're working with PDFs in .NET, you might come across a need to get a particular annotation from a PDF document. In this guide, we'll show you how to use Aspose.PDF for .NET to get a particular annotation from a PDF document using C#.

Follow these simple steps to get a particular annotation from a PDF document:

## Step 1: Get Particular Annotation from PDF Document

First, make sure you have the Aspose.PDF for .NET library installed and referenced in your project.

Next, create a new instance of the Document class and load your PDF document using the path to the document directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## Step 2: You can get a particular annotation using the following code:

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

This code retrieves the second annotation on the second page of the PDF document.

## Step 3: Finally, you can get the properties of the annotation using the following code:

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

This code displays the title, subject, and contents of the annotation in the console.


### Example Source Code for Get Particular Annotation using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

// Get particular annotation
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

// Get annotation properties
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

