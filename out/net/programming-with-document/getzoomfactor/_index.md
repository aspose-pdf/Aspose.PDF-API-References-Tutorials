---
title: Get Zoom Factor
linktitle: Get Zoom Factor
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to get the zoom factor of a PDF file with this step-by-step guide.
type: docs
weight: 210
url: /content/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET is a PDF manipulation library that provides many features to perform various operations on PDF documents. One of these features is the ability to get the zoom factor of a PDF file. In this tutorial, we will explain how to use Aspose.PDF for .NET to get the zoom factor of a PDF file using C# source code.


## Step 1: Instantiate new Document object

The first step to getting the zoom factor of a PDF file using Aspose.PDF for .NET is to instantiate a new `Document` object. The `Document` object represents a PDF document that can be loaded from a file or a stream.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate new Document object
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

In the above code, we have created a `Document` object by passing the path of the PDF file to the constructor of the `Document` class. You need to replace "YOUR DOCUMENT DIRECTORY" with the actual path of the directory where your PDF file is located.

## Step 2: Create GoToAction object

The next step is to create a `GoToAction` object. A `GoToAction` object represents an action that goes to a specific destination in a PDF document. In our case, we want to get the zoom factor of the PDF file, so we will use the `OpenAction` property of the `Document` object to get the `GoToAction` object.

```csharp
// Create GoToAction object
GoToAction action = doc.OpenAction as GoToAction;
```

In the above code, we have created a `GoToAction` object by casting the `OpenAction` property of the `Document` object to `GoToAction`.

## Step 3: Get the Zoom factor of PDF file

The third step is to get the zoom factor of the PDF file. We can get the zoom factor of the PDF file by accessing the `Destination` property of the `GoToAction` object and then casting it to `XYZExplicitDestination`. The `XYZExplicitDestination` class represents a destination in a PDF document that specifies the coordinates and zoom factor to go to.

```csharp
// Get the Zoom factor of PDF file
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Document zoom value;
```

In the above code, we have accessed the `Destination` property of the `GoToAction` object and then cast it to `XYZExplicitDestination`. After that, we have accessed the `Zoom` property of the `XYZExplicitDestination` object to get the zoom factor of the PDF file.

## Step 4: Output the Zoom factor

The final step is to output the zoom factor of the PDF file. We can use the `System.Console.WriteLine`

```csharp
// Get the Zoom factor of PDF file
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Document zoom value;
```        

### Example Source Code for Get Zoom Factor using Aspose.PDF for .NET

Here's the complete example source code for Get Zoom Factor using Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate new Document object
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Create GoToAction object
GoToAction action = doc.OpenAction as GoToAction;

// Get the Zoom factor of PDF file
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Document zoom value;
```
