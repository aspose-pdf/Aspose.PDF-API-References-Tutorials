---
title: lnk Annotation Line Width
linktitle: lnk Annotation Line Width
second_title: Aspose.PDF for .NET API Reference
description: This article provides a step-by-step guide for setting the line width of the lnk Annotation using Aspose.PDF for .NET.
type: docs
weight: 110
url: /net/annotations/lnkannotationlinewidth/
---
Aspose.PDF is a powerful and widely-used tool for working with PDF files in .NET applications. It provides a variety of features for creating, editing, and manipulating PDF files, including the ability to add annotations to pages. In this tutorial, we will explain how to set the line width of a link annotation using Aspose.PDF for .NET.

Once you have these prerequisites, create a new console application project in Visual Studio. Then, add a reference to the Aspose.PDF for .NET library by right-clicking on the project in the Solution Explorer, selecting "Manage NuGet Packages," and searching for "Aspose.PDF" in the NuGet Package Manager.

To add a lnk annotation to a PDF document, follow these steps:

## Create a new `Document` object.
```csharp
Document doc = new Document();
```
## Add a new page to the document.
```csharp
doc.Pages.Add();
```
## Create a list of `Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
## Create a new `LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
## Create a new `Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Add the gesture to the list of ink gestures.
```csharp
inkList.Add(gesture);
```
## Create a new `InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Set the subject and title of the annotation.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Set the color of the annotation.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
## Create a new `Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Add the annotation to the page.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Save the document to a file.
```c// Save output file
doc.Save(dataDir);


```
### The example shows lnk Annotation Line Width with Aspose.PDF for .NET

```csharp


// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Save output file
doc.Save(dataDir);


```

