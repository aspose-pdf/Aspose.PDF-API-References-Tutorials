---
title: Set Zoom Factor
linktitle: Set Zoom Factor
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set the zoom factor for PDF files using Aspose.PDF for .NET with our step-by-step guide.
type: docs
weight: 340
url: /content/net/programming-with-document/setzoomfactor/
---
Aspose.PDF for .NET is a powerful API that allows developers to work with PDF documents in their .NET applications. One of the features it provides is the ability to set the zoom factor of a PDF document. In this step-by-step guide, we will explain how to use Aspose.PDF for .NET to set the zoom factor of a PDF document using the provided C# source code.

## Step 1: Set the path to the document directory

The first step is to set the path to the directory where the PDF document is located. This can be done by setting the `dataDir` variable to the directory path. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace "YOUR DOCUMENT DIRECTORY" with the actual directory path where your PDF document is located.

## Step 2: Instantiate a new Document object

To work with a PDF document using Aspose.PDF for .NET, we need to create a new `Document` object and load the PDF file into it. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

This code will create a new `Document` object and load the PDF file named "SetZoomFactor.pdf" from the `dataDir` directory into it.

## Step 3: Set the zoom factor

Once the `Document` object is created, we can set the zoom factor of the PDF document. In the following code, we set the zoom factor to 50%.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

This code sets the zoom factor to 50% by creating a new `GoToAction` object and passing a `XYZExplicitDestination` object with a zoom factor of 50% to it. The `OpenAction` property of the `Document` object is then set to this `GoToAction` object.

## Step 4: Save the PDF document

Finally, we can save the modified PDF document to a new file. In the following code, we save the PDF document to a new file named "Zoomed_pdf_out.pdf" in the `dataDir` directory.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Example source code for Set Zoom Factor using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate new Document object
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// Save the document
doc.Save(dataDir);
```

## Conclusion

Aspose.PDF for .NET provides a simple and efficient way to set the zoom factor of a PDF document using C# code. By following the above steps, you can easily modify the zoom factor of any PDF document in your .NET application.