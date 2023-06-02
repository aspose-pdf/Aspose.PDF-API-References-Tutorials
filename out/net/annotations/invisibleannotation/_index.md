---
title: Invisible Annotation
linktitle: Invisible Annotation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to invisibly annotate PDFs using C# source code with Aspose.PDF for .NET. Step-by-step guide.
type: docs
weight: 100
url: /content/net/annotations/invisibleannotation/
---

Annotations in PDF documents are a powerful feature that allows you to add extra information or notes to a document without changing the actual content. They can be used to highlight text, draw attention to specific areas of a document, or add comments or feedback.

There are many different types of annotations that you can use in PDF documents, including:

- Text Annotations
- Link Annotations
- Stamp Annotations
- Sound Annotations
- File Attachment Annotations
- and many more

## Step 1: Creating an Invisible Annotation in a PDF Document Using Aspose.PDF for .NET

To create an invisible annotation in a PDF document using Aspose.PDF for .NET, we first need to create a `FreeTextAnnotation` object and specify the location and size of the annotation.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

In the code above, we create a `FreeTextAnnotation` object and specify the location of the annotation on page 2 of the PDF document. We also specify the font type, size, and color for the text that will be displayed in the annotation.

## Step 2: Adding Characteristics to the Invisible Annotation

Next, we can add some characteristics to the annotation, such as a border color, background color, or opacity.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

In the code above, we set the border color of the annotation to red.

## Step 3: Setting the Annotation Flags

After we have created the annotation and set its characteristics, we can specify the annotation flags. In this tutorial, we want the annotation to be printable, but not viewable.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Step 4: Saving the Modified PDF Document

Finally, we can save the modified PDF document with the new invisible annotation.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Example Source Code for How to Invisible Annotation using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Save output file
doc.Save(dataDir);
// ExEnd:InvisibleAnnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```