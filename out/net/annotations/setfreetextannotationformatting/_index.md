---
title: Set Free Text Annotation Formatting
linktitle: Set Free Text Annotation Formatting
second_title: Aspose.PDF for .NET API Reference
description: This article provides a step-by-step guide on how to create a free text annotation and specify its contents using Aspose.PDF for .NET
type: docs
weight: 140
url: /content/net/annotations/setfreetextannotationformatting/
---

Aspose.PDF for .NET is a powerful and easy-to-use PDF document manipulation API that allows you to work with PDF files programmatically in your .NET applications. One of the features provided by Aspose.PDF for .NET is the ability to set free text annotation formatting in PDF documents. In this article, we will walk you through the step-by-step process of setting free text annotation formatting using Aspose.PDF for .NET.

## Prerequisites

Before we get started, make sure that you have the following prerequisites:

- Microsoft Visual Studio 2010 or later
- Aspose.PDF for .NET
- Basic knowledge of C#



## Step 1: Create a new C# console application

First, create a new C# console application in Microsoft Visual Studio. To create a new console application, select "File" > "New" > "Project" > "Visual C#" > "Console Application" from the main menu.

## Step 2: Add reference to Aspose.PDF for .NET

Next, add a reference to Aspose.PDF for .NET in your project. To do this, right-click on your project in the "Solution Explorer" pane, select "Add" > "Reference", and then browse to the location where you saved the Aspose.PDF for .NET DLL file. Select the DLL file and click "OK" to add the reference to your project.

## Step 3: Set up the environment

After adding the reference to Aspose.PDF for .NET, you need to set up the environment. To do this, create a new string variable called "dataDir" and set it to the path of the directory where your PDF document is located. Replace "YOUR DOCUMENT DIRECTORY" in the code below with the actual path of your document directory:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 4: Open the PDF document

Once you have set up the environment, you can open the PDF document using the following code:

```csharp
// Open document
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Replace "SetFreeTextAnnotationFormatting.pdf" with the actual name of your PDF document.

## Step 5: Set up default appearance

To set up the default appearance of the free text annotation, you need to instantiate the DefaultAppearance object with the desired font, font size, and color. In this tutorial, we are setting the font to "Arial", font size to 28, and color to red.

```csharp
// Instantiate DefaultAppearance object
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## Step 6: Create a free text annotation

Now that you have set up the default appearance, you can create a free text annotation using the following code:

```csharp
// Create annotation
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

The above code creates a new free text annotation on the second page of the PDF document. The annotation will be positioned at (200, 400) and will have a width of 400 and a height of 600.

## Step 7: Specify the contents of the annotation

After creating the free text annotation, you can specify the contents of the annotation using the following code:

```csharp
// Specify the contents of annotation
freetext.Contents = "Free Text
```

### Example source code for Set Free Text Annotation Formatting using Aspose.PDF for .NET
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Instantiate DefaultAppearance object
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Create annotation
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Specify the contents of annotation
freetext.Contents = "Free Text";
// Add anootation to annotations collection of page
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Save the updated document
pdfDocument.Save(dataDir);            
```
