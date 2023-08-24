---
title: Extract Links In PDF File
linktitle: Extract Links In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily extract links in PDF file using Aspose.PDF for .NET.
type: docs
weight: 50
url: /it/net/programming-with-links-and-actions/extract-links/
---
Extracting links in PDF file allows you to recover all the hypertext links present in the document. With Aspose.PDF for .NET, you can easily extract these links by following the following source code:

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

### FAQ's for extract links in PDF file

#### Q: What is link extraction in a PDF file?

A: Link extraction in a PDF file refers to the process of recovering all the hypertext links present within the document. This allows you to retrieve URLs, internal document links, and other interactive elements.

#### Q: How can link extraction benefit my PDF document analysis?

A: Link extraction is valuable for various purposes, such as content validation, data mining, and analysis. It enables you to identify and catalog all the links within a PDF document for further exploration.

#### Q: How does Aspose.PDF for .NET support link extraction?

A: Aspose.PDF for .NET provides powerful APIs to extract links from PDF documents with ease. The step-by-step tutorial outlined in this guide demonstrates how to extract links using C#.

#### Q: Can I extract specific types of links, such as hyperlinks or internal document links?

A: Yes, you can selectively extract specific types of links using the `AnnotationSelector` class. This allows you to filter and retrieve the desired links based on your requirements.

#### Q: Is it possible to extract links from specific pages of a PDF document?

A: Absolutely! You can extract links from specific pages of a PDF document by specifying the target page using the `Document.Pages` collection. This enables you to focus on particular sections.

#### Q: What format are the extracted links returned in?

A: The extracted links are returned as instances of the `Annotation` class. You can process and analyze these annotations to retrieve link details, including target URLs and link types.

#### Q: How can I verify that link extraction is accurate?

A: By following the tutorial and sample code provided, you can ensure accurate link extraction. You can analyze the extracted annotations and validate the URLs and link attributes.

#### Q: Are there any limitations when extracting links?

A: While link extraction is a powerful feature, it's important to consider the structure of the PDF document. Links embedded within images, tables, or multimedia content may require additional handling.

#### Q: Can I extract links from password-protected PDF documents?

A: Aspose.PDF for .NET can extract links from password-protected PDF documents as long as you provide the necessary authentication credentials when opening the document.