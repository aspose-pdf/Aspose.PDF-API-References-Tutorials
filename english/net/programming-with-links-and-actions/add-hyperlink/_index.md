---
title: Add Hyperlink
linktitle: Add Hyperlink
second_title: Aspose.PDF for .NET API Reference
description: Easily add interactive hyperlinks in your PDF files with Aspose.PDF for .NET.
type: docs
weight: 10
url: /net/programming-with-links-and-actions/add-hyperlink/
---

Adding hyperlinks in a PDF document allows you to create interactive hyperlinks to other pages, websites, or destinations in the document. With Aspose.PDF for .NET, you can easily add hyperlinks by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to add a hyperlink to. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

Now we will open the PDF document to which we want to add a hyperlink using the following code:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## Step 4: Create a link

In this step, we will create a hyperlink using the `LinkAnnotation` annotation. We will specify the contact details and area of the link, the type of link and the content of the link. Here is the corresponding code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## Step 5: Add additional text

In addition to the hyperlink, we can also add additional text using the `FreeTextAnnotation` annotation. We will specify coordinates, text appearance and text content. Here is the corresponding code:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## Step 6: Save the updated file

Now let's save the updated PDF file using the `Save` method of the `document` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Sample source code for Add Hyperlink using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Create link
Page page = document.Pages[1];
// Create Link annotation object
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Create border object for LinkAnnotation
Border border = new Border(link);
// Set the border width value as 0
border.Width = 0;
// Set the border for LinkAnnotation
link.Border = border;
// Specify the link type as remote URI
link.Action = new GoToURIAction("www.aspose.com");
// Add link annotation to annotations collection of first page of PDF file
page.Annotations.Add(link);
// Create Free Text annotation
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// String to be added as Free text
textAnnotation.Contents = "Link to Aspose website";
// Set the border for Free Text Annotation
textAnnotation.Border = border;
// Add FreeText annotation to annotations collection of first page of Document
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Save updated document
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Conclusion

Congratulation ! You now have a step-by-step guide to adding hyperlinks with Aspose.PDF for .NET. You can use this code to create interactive links in your PDF documents.
