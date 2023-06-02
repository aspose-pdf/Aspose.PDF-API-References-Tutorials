---
title: Get Page Count
linktitle: Get Page Count
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to get the page count of a PDF file using Aspose.PDF for .NET. Easy to follow and implement in your projects.
type: docs
weight: 80
url: /net/programming-with-pdf-pages/get-page-count/
---
In this tutorial, we'll walk you through the step-by-step process to get the page count of a PDF file using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to get the page count of a PDF file using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Instantiate a Document object
First, you need to instantiate a Document object using the Document class of Aspose.PDF.

```csharp
Document doc = new Document();
```

## Step 2: Add a page to the document
Then you can add a page to the document using the `Add()` method of the document's Pages collection.

```csharp
Page page = doc.Pages.Add();
```

## Step 3: Create page content
Now you can create page content by adding TextFragment objects to the Page object's Paragraphs collection. In this example, we add a TextFragment repeated 300 times to simulate a document with longer content.

```csharp
for (int i = 0; i < 300; i++)
page.Paragraphs.Add(new TextFragment("Page count test"));
```

## Step 4: Processing Paragraphs and Getting Page Count
Once you have added the content to the page, you need to process the document paragraphs by calling the `ProcessParagraphs()` method. This allows Aspose.PDF to calculate the number of pages accurately.

```csharp
doc.ProcessParagraphs();
```

## Step 5: Displaying the number of pages
Finally, you can view the number of pages in the document by accessing the `Count` property of the Pages collection.

```csharp
Console.WriteLine("Number of pages in document = " + doc.Pages.Count);
```

### Sample source code for Get Page Count using Aspose.PDF for .NET 

```csharp

// Instantiate Document instance
Document doc = new Document();
// Add page to pages collection of PDF file
Page page = doc.Pages.Add();
// Create loop instance
for (int i = 0; i < 300; i++)
	// Add TextFragment to paragraphs collection of page object
	page.Paragraphs.Add(new TextFragment("Pages count test"));
// Process the paragraphs in PDF file to get accurate page count
doc.ProcessParagraphs();
// Print number of pages in document
Console.WriteLine("Number of pages in document = " + doc.Pages.Count);

```

## Conclusion
In this tutorial, we learned how to get the page count of a PDF file using Aspose.PDF for .NET. By following the steps outlined above, you can easily implement this functionality in your own projects. Feel free to explore the Aspose.PDF documentation further to discover other useful features for working with PDF files.

