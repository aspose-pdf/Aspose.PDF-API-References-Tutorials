---
title: Add PDF Annotation
linktitle: Add Annotation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add text PDF annotations with Aspose.PDF for .NET using this C# source code. Customize your annotations with specific details and icons.
type: docs
weight: 10
url: /de/net/annotations/addannotation/
---
Adding annotations to PDF documents is a powerful feature that can enhance collaboration and review processes. Aspose.PDF for .NET makes it easy to add annotations programmatically to PDF documents using C#. In this guide, we will explain step-by-step how to use Aspose.PDF for .NET to add annotations to a PDF document.

## Step 1: Create a New Project and Install Aspose.PDF for .NET

Before we start writing the code for adding annotations, we need to create a new project and install Aspose.PDF for .NET. To install Aspose.PDF for .NET, follow these steps:

1. Open Visual Studio and create a new C# project.
2. Right-click on the project in the Solution Explorer and select "Manage NuGet Packages".
3. Search for "Aspose.PDF" and select "Install".

Once the installation is complete, we can start writing the code.

## Step 2: Open the PDF Document

The first step in adding annotations is to open the PDF document. We can use the following code to open the document:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

In this code, we specify the path to the PDF document we want to open. Make sure to replace "YOUR DATA DIRECTORY" with the actual path to your data directory.

## Step 3: Create the Annotation

To add an annotation, we need to create a new instance of the `TextAnnotation` class. We can use the following code to create a new text annotation:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

In this code, we create a new text annotation on the second page of the PDF document. We also set the title, subject, state, contents, open, and icon properties of the annotation.

## Step 4: Customize the Annotation

We can customize the appearance of the annotation using the `Border` class. We can use the following code to customize the border of the annotation:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

In this code, we create a new `Border` object and set its width and dash properties. We then set the `Border` property of the annotation to the new `Border` object. Finally, we set the `Rect` property of the annotation to specify its position and size.

## Step 5: Add the Annotation to the PDF Document

Once we have created and customized the annotation, we need to add it to the PDF document. We can use the following code to add the annotation to the PDF document:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

In this code, we add the annotation to the annotations collection of the second page of the PDF document.

## Step 6: Save the Output File

Finally, we need to save the PDF document with the added annotation. We can use the following code to save the output file:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Example source code for Adding Annotation using Aspose.PDF for .NET


```csharp   
 // The path to the documents directory.
string dataDir = "YOUR DATA DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Create annotation
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Add annotation in the annotations collection of the page
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Save output file
pdfDocument.Save(dataDir);
```
This code demonstrates how to add a text annotation with a specific title, subject, state, contents, and icon to a PDF page using Aspose.PDF for .NET. You can modify this code according to your requirements for adding annotations to your PDF documents. Just remember to replace YOUR DATA DIRECTORY with the actual directory path where your PDF file is located and where you want to save the output file.

## Conclusion

Adding annotations to PDF documents using Aspose.PDF for .NET offers a valuable tool for enhancing document collaboration and review processes. By following the step-by-step guide provided in this article, developers can seamlessly integrate annotation capabilities into their C# applications.

### FAQ's

#### Q: What types of annotations can be added using Aspose.PDF for .NET?

A: Aspose.PDF for .NET supports various types of annotations, including text annotations, stamps, links, shapes, and more. Developers can customize the appearance and properties of these annotations to suit their specific needs.

#### Q: Can I add annotations to specific pages in a multi-page PDF document?

A: Yes, Aspose.PDF for .NET allows you to specify the page where you want to add the annotation. You can choose a specific page or add annotations to multiple pages as needed.

#### Q: How do I customize the appearance of annotations?

A: Annotations can be customized using properties such as border width, color, dash style, text style, and more. Aspose.PDF for .NET provides a rich set of options to tailor the appearance of annotations.

#### Q: Is it possible to add hyperlinks as annotations using Aspose.PDF for .NET?

A: Yes, you can add hyperlinks as annotations to PDF documents using Aspose.PDF for .NET. Hyperlink annotations can be used to link to external URLs or specific locations within the same document.

#### Q: Can annotations be added to existing PDF documents without altering the original content?

A: Yes, Aspose.PDF for .NET adds annotations as additional elements without altering the original content of the PDF document. The original PDF content remains intact.