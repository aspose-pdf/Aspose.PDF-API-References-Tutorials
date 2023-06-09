---
title: Remove Graphics Objects
linktitle: Remove Graphics Objects
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to remove graphic objects from a PDF document using Aspose.PDF for .NET. Customize and clean up your PDFs.
type: docs
weight: 30
url: /content/net/programming-with-operators/remove-graphics-objects/
---
In this tutorial, we will provide you with a step-by-step guide on how to remove graphic objects from a PDF document using Aspose.PDF for .NET. Aspose.PDF is a powerful library that allows you to create, manipulate and convert PDF documents programmatically. Using the operators provided by Aspose.PDF, you can target and remove specific graphic objects from a PDF page.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Visual Studio installed with .NET framework.
2. The Aspose.PDF library for .NET.

## Step 1: Project Setup

To get started, create a new project in Visual Studio and add a reference to the Aspose.PDF for .NET library. You can download the library from Aspose official website and install it on your machine.

## Step 2: Import the necessary namespaces

In your C# code file, import the namespaces required to access the classes and methods provided by Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Step 3: Loading the PDF document

Use the following code to load the PDF document:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "RemoveGraphicsObjects.pdf");
Page page = doc.Pages[2];
OperatorCollection oc = page.Contents;
```

Be sure to specify the actual path of the PDF file on your machine and adjust the page number as needed.

## Step 4: Deleting graphic objects

Use the following code to remove graphic objects from the PDF page:

```csharp
Operator[] operators = new Operator[] {
newStroke(),
new ClosePathStroke(),
newFill()
};
oc.Delete(operators);
```

The code above removes graphical objects identified by the Stroke, Path Close, and Fill operators.

### Sample source code for Remove Graphics Objects using Aspose.PDF for .NET
 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir+ "RemoveGraphicsObjects.pdf");
Page page = doc.Pages[2];
OperatorCollection oc = page.Contents;
// Used path-painting operators
Operator[] operators = new Operator[] {
		new Aspose.Pdf.Operators.Stroke(),
		new Aspose.Pdf.Operators.ClosePathStroke(),
		new Aspose.Pdf.Operators.Fill()
};
oc.Delete(operators);
doc.Save(dataDir+ "No_Graphics_out.pdf");

```

## Conclusion

In this tutorial, you learned how to remove graphical objects from a PDF document using Aspose.PDF for .NET. Using the operators provided by Aspose.PDF, you can target and remove specific graphic objects from a PDF page. This allows you to customize and clean up the content of your PDF documents according to your needs.
