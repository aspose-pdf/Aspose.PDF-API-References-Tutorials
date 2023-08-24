---
title: Create Document Link
linktitle: Create Document Link
second_title: Aspose.PDF for .NET API Reference
description: Easily create links to other PDF documents with Aspose.PDF for .NET.
type: docs
weight: 30
url: /it/net/programming-with-links-and-actions/create-document-link/
---
Linking to another document in a PDF file allows you to create clickable links that redirect users to other PDF documents. With Aspose.PDF for .NET, you can easily create such links by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file to which you want to add a link to another document. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we will open the PDF document to which we want to add the link to another document using the following code:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Step 4: Create the link to another document

In this step, we will create the link to another document using the `LinkAnnotation` annotation. We will specify the coordinates and area of the link, as well as the navigation action to an external document. Here is the corresponding code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Step 5: Save the updated file

Now let's save the updated PDF file using the `Save` method of the `document` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Sample source code for Create Document Link using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Create link
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Save updated document
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusion

Congratulation ! You now have a step-by-step guide to linking to other documents with Aspose.PDF for .NET. You can use this code to create clickable links in your PDF files, redirecting users to other documents.

Be sure to check out the official Aspose.PDF documentation for more information on the advanced features of interactive links.

### FAQ's for create document link

#### Q: What are document links in PDF files?

A: Document links in PDF files are clickable links that direct users to other PDF documents. These links enhance navigation by providing an efficient way to connect related content and facilitate a seamless reading experience.

#### Q: How can I benefit from creating document links?

A: Creating document links allows you to establish connections between different sections or topics within your PDF documents. This feature enables users to access supplementary information or related materials with ease.

#### Q: How does Aspose.PDF for .NET support the creation of document links?

A: Aspose.PDF for .NET simplifies the process of creating document links by providing a comprehensive set of APIs. The step-by-step tutorial outlined in this guide demonstrates how to add document links to your PDF files.

#### Q: Can I customize the appearance of document links?

A: Absolutely! Aspose.PDF for .NET offers customization options for document link appearance, including color, style, and hover effects. You can tailor the appearance to match your document's design.

#### Q: Is it possible to link to specific sections or pages within another document?

A: Yes, you can create links that navigate users to specific pages or sections within another PDF document. Aspose.PDF for .NET provides the flexibility to define the target location within the linked document.

#### Q: How can I ensure that my document links are functional?

A: By following the provided tutorial and sample code, you can confidently create functional document links. You can test the links by opening the generated PDF document and clicking on the links.

#### Q: Can I create multiple document links within a single PDF file?

A: Certainly! You can create multiple document links within a single PDF document using the `LinkAnnotation` annotation. This allows you to provide users with access to various related documents from different sections.

#### Q: Are there any limitations when linking to external documents?

A: When linking to external documents, ensure that the linked documents are accessible and located in the specified paths. It's also important to consider user permissions and the compatibility of linked documents.

#### Q: Can I link to documents stored on the web or online repositories?

A: While this tutorial focuses on linking to local documents, Aspose.PDF for .NET also supports linking to web URLs or online repositories. You can adapt the provided code to create web-based document links.