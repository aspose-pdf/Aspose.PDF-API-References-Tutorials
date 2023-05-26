---
title: Add lnk Annotation
linktitle: Add lnk Annotation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add Ink Annotation feature to PDF documents in C# using Aspose.PDF for .NET with step-by-step guide and full source code.
type: docs
weight: 20
url: /net/annotations/addlnkannotation/
---
Aspose.PDF for .NET is a powerful library that enables developers to perform various PDF operations. One such operation is adding Ink Annotation to PDF documents. In this article, we will provide a step-by-step guide to explain the C# source code for adding Ink Annotation using Aspose.PDF for .NET. Let's get started!

## Understanding the Ink Annotation Feature of Aspose.PDF for .NET

Before diving into the C# source code, let's first understand what Ink Annotation is and its uses.

Ink Annotation is a way to draw freeform ink annotations on PDF documents. It allows you to create annotations with a stylus or a mouse. This feature is useful in situations where you need to draw diagrams, sketches, or other types of annotations.

## Step 1: Creating a New Document

The first step in adding Ink Annotation to a PDF document is to create a new instance of the Document class. This is achieved using the following code snippet:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Here, we create a new instance of the Document class and add a new page to it.

## Step 2: Creating Ink Annotation

The next step is to create an instance of the InkAnnotation class. This is done using the following code snippet:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Here, we first create a rectangle using the System.Drawing.Rectangle class and convert it to Aspose.Pdf.Rectangle using the FromRect method. We then create an instance of the InkAnnotation class using the rectangle, a list of points, and the page where the annotation is added.

We then set various properties of the InkAnnotation, such as the title, color, cap style, border, and opacity. Finally, we add the annotation to the page using the Annotations.Add method.

## Step 3: Saving the Document

The final step is to save the PDF document with the Ink Annotation added. This is achieved using the following code snippet:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Here, we concatenate the output file name to the data directory and save the document using the Save method.

### Example source code for Adding Ink Annotation using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Save output file
doc.Save(dataDir);
```
