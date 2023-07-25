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

## Step 1: Create a new `Document` object.
```csharp
Document doc = new Document();
```
## Step 2: Add a new page to the document.
```csharp
doc.Pages.Add();
```
## Step 3: Create a list of `Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
## Step 4: Create a new `LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
## Step 5: Create a new `Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Step 6: Add the gesture to the list of ink gestures.
```csharp
inkList.Add(gesture);
```
## Step 7: Create a new `InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Step 8: Set the subject and title of the annotation.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Step 9: Set the color of the annotation.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
## Step 10: Create a new `Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Step 11: Add the annotation to the page.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Step 12: Save the document to a file.
```csharp
// Save output file
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

## Conclusion

In this tutorial, we learned how to set the line width of a link annotation in a PDF document using Aspose.PDF for .NET. Aspose.PDF for .NET provides a wide range of tools and features for working with PDF documents, including the ability to create and customize link annotations. By following the step-by-step guide and using the provided C# source code, developers can easily add interactive links to their PDF documents, enhancing the user experience and interactivity of their applications. Aspose.PDF for .NET is a versatile library that empowers .NET developers to work with PDF files efficiently and effectively.

### FAQ's

#### Q: What is a link annotation in a PDF document?

A: A link annotation in a PDF document is an interactive element that allows you to create hyperlinks or actions that direct the user to another location within the same document, an external website, or a different PDF document.

#### Q: How can I set the line width of a link annotation using Aspose.PDF for .NET?

A: To set the line width of a link annotation using Aspose.PDF for .NET, you can create an `InkAnnotation` object and specify the line width property.

#### Q: What properties can be customized for a link annotation in Aspose.PDF for .NET?

A: You can customize various properties of a link annotation in Aspose.PDF for .NET, such as its location, size, color, border properties (width, style, dash pattern, and effect), subject, title, and visibility.

#### Q: Can I create a link annotation that contains multiple ink gestures?

A: Yes, you can create a link annotation that contains multiple ink gestures by adding multiple `Point` arrays to the `InkAnnotation` object.

#### Q: How can I add a link annotation to a specific page of the PDF document?

A: To add a link annotation to a specific page of the PDF document, you need to specify the page number when creating the `InkAnnotation` object. For example, `new InkAnnotation(doc.Pages[1], ...)` adds the link annotation to the first page.
