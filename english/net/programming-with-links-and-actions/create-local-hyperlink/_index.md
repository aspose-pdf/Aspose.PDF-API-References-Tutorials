---
title: Create Local Hyperlink
linktitle: Create Local Hyperlink
second_title: Aspose.PDF for .NET API Reference
description: Easily create local hyperlinks in a PDF file using Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/programming-with-links-and-actions/create-local-hyperlink/
---

Creating local hyperlinks in a PDF file lets you create clickable links that take users to other pages in the same PDF document. With Aspose.PDF for .NET, you can easily create such links by following the following source code:

## Step 1: Import Required Libraries

Before you begin, you need to import the necessary libraries for your C# project. Here is the necessary import directive:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder where you want to save the resulting PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Create an instance of Document

We will create an instance of the `Document` class to represent our PDF document. Here is the corresponding code:

```csharp
Document doc = new Document();
```

## Step 4: Add page and text with hyperlinks

In this step, we are going to add a page to our PDF document and add some text containing local hyperlinks. We will define the target pages for each link. Here is the corresponding code:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Step 5: Save the updated document

Now let's save the updated PDF file using the `Save` method of the `doc` object. Here is the corresponding code:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Create Local Hyperlink using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create Document instance
Document doc = new Document();
// Add page to pages collection of PDF file
Page page = doc.Pages.Add();
// Create Text Fragment instance
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Create local hyperlink instance
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Set target page for link instance
link.TargetPageNumber = 7;
// Set TextFragment hyperlink
text.Hyperlink = link;
// Add text to paragraphs collection of Page
page.Paragraphs.Add(text);
// Create new TextFragment instance
text = new TextFragment("link page number test to page 1");
// TextFragment should be added over new page
text.IsInNewPage = true;
// Create another local hyperlink instance
link = new LocalHyperlink();
// Set Target page for second hyperlink
link.TargetPageNumber = 1;
// Set link for second TextFragment
text.Hyperlink = link;
// Add text to paragraphs collection of page object
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Save updated document
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusion

Congratulation ! Now you have a step by step guide to create local hyperlinks in a PDF using Aspose.PDF for .NET. You can use this code to create clickable links that take users to other pages in the same document.

Be sure to check out the official Aspose.PDF documentation for more information on advanced hyperlinking features.
