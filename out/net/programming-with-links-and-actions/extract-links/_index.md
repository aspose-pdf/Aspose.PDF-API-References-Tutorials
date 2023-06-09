---
title: Extract Links
linktitle: Extract Links
second_title: Aspose.PDF for .NET API Reference
description: Easily extract links from a PDF document using Aspose.PDF for .NET.
type: docs
weight: 50
url: /content/net/programming-with-links-and-actions/extract-links/
---

Extracting links from a PDF document allows you to recover all the hypertext links present in the document. With Aspose.PDF for .NET, you can easily extract these links by following the following source code:

## Step 1: Import Required Libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file from which you want to extract the links. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

We will open the PDF document using the `Document` class. Here is the corresponding code:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Step 4: Extract links

In this step, we will extract the links present in the PDF document using the `AnnotationSelector` class. Here is the corresponding code:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Step 5: Save the updated document

Now let's save the updated PDF file using the `Save` method of the `document` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Sample source code for Extract Links using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Extract actions
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Save updated document
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You now have a step-by-step guide to extract links from a PDF document using Aspose.PDF for .NET. You can use this code to retrieve all the hyperlinks present in the document.

Be sure to check out the official Aspose.PDF documentation for more information on advanced link extraction features.