---
title: Create Document Link
linktitle: Create Document Link
second_title: Aspose.PDF for .NET API Reference
description: Easily create links to other PDF documents with Aspose.PDF for .NET.
type: docs
weight: 30
url: /net/programming-with-links-and-actions/create-document-link/
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

### Sample source code for Create Document Link using Aspose.Words for .NET 
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
