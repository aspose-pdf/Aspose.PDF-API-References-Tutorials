---
title: Add Layers
linktitle: Add Layers
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add layers to PDF files using Aspose.PDF for .NET. Step-by-step guide with code tutorials for creating and saving layered PDFs.
type: docs
weight: 20
url: /content/net/programming-with-document/addlayers/
---

To add layers to a PDF file, we will utilize Aspose.PDF for .NET. This library allows us to work with PDF files in .NET applications effectively. Follow the step-by-step instructions below to add layers using Aspose.PDF for .NET.

## Step 1: Create a New PDF Document

Begin by creating a new instance of the `Document` class provided by Aspose.PDF for .NET. This will serve as the PDF document where we will add the layers.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Step 2: Add a Page to the Document

Next, add a page to the document using the `Add` method of the `Pages` collection in the `Document` class.

```csharp
Page page = doc.Pages.Add();
```

## Step 3: Create and Add Layers to the Page

Create instances of the `Layer` class for each layer you want to add to the PDF file. Specify a unique identifier and a name for each layer.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

In this tutorial, we have added three layers with different colors and names to the page.

## Step 4: Save the PDF File

Save the modified PDF file using the `Save` method of the `Document` class.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

This code will save the modified PDF file to the specified directory.

### Example source code for Adding Layers to PDF Pages using Aspose.PDF for .NET

```csharp            
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Conclusion

In this article, we have provided a step-by-step guide to adding layers to PDF files using Aspose.PDF for .NET. By following the instructions and utilizing the provided code tutorials, you can easily incorporate layers into your PDF documents. Layers allow you to organize and control the visibility of content, providing a more interactive and customizable experience for your users.