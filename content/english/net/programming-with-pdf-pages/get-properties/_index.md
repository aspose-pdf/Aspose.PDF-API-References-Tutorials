---
title: Get PDF Properties
linktitle: Get PDF Properties
second_title: Aspose.PDF for .NET API Reference
description: Learn how to efficiently extract PDF properties using Aspose.PDF for .NET. Step-by-step guide with code examples and best practices.
type: docs
weight: 100
url: /net/programming-with-pdf-pages/get-properties/
---
## Introduction

When it comes to manipulating PDFs programmatically, Aspose.PDF for .NET is one of those reliable tools that stand out. Whether you're looking to extract information, modify documents, or simply read PDF properties, this library provides a suite of functionalities to make your task easier. In this guide, we're going to dive deep into how to get PDF properties, a task that can seem daunting at first but becomes a breeze with the right tools. So, buckle up! We’ll explore either the technicalities or the possibilities that come with working with PDF files.

## Prerequisites

Before jumping into the code, it’s essential to ensure you have all the necessary components in place. This section will help you get set up to start working with the Aspose.PDF library.

1. .NET Environment: Ensure you have a working .NET environment. You can use Visual Studio or any other suitable IDE.
   
2. Aspose.PDF for .NET: You need to have Aspose.PDF installed. You can download the library from the [Aspose PDF Releases](https://releases.aspose.com/pdf/net/) page.

3. Basic Understanding of C#: Familiarity with C# programming will be helpful as we’ll be writing the code in C#.

4. PDF File: You need a sample PDF file to work with. For this example, we’ll refer to "GetProperties.pdf".

### Setting Up Your Project

Once you've got your tools and the PDF file ready, here’s how you can set up your project:

1. Create a New Project: Open your IDE and create a new C# project.

2. Add References: Include the Aspose.PDF assembly. You can do this via NuGet Package Manager or by adding a reference to the DLL directly.

3. Prepare Your PDF File: Place your sample "GetProperties.pdf" in a directory that your code can access easily, say `"YOUR DOCUMENT DIRECTORY"`.

## Import Packages

Once your project setup is complete, the first thing you need to do is import the necessary namespaces. The Aspose.PDF library provides various classes that allow you to interact with PDF documents.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

This simple step ensures that you have access to the classes needed to manipulate and extract information from your PDF file efficiently.

Now, let’s break down the task of fetching PDF properties into actionable steps. This section will guide you through each step so you can easily follow along and understand how the process works.

## Step 1: Define the Document Directory

The first step in our journey is to define where our PDF document resides. We want to point to the location of "GetProperties.pdf".

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

This line of code ensures that we specify where Aspose can find the PDF file that we want to work with.

## Step 2: Open the PDF Document

Next up, we'll open the PDF document using the `Document` class from the Aspose.PDF library. This is a crucial step because it loads the PDF into memory.

```csharp
// Open document
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

By executing this line, we create an instance of the `Document` class that represents our PDF file, making all its properties accessible.

## Step 3: Access the Page Collection

After opening the document, we need to access the pages within that document. Each PDF can have multiple pages, so we'll work with a collection that holds all the pages.

```csharp
// Get page collection
PageCollection pageCollection = pdfDocument.Pages;
```

Think of `PageCollection` as an index that helps us navigate through the pages in our PDF document.

## Step 4: Get a Specific Page

Now that we have access to our pages, it’s time to dig deeper. We will retrieve a specific page from the collection; in this case, we'll get the first page.

```csharp
// Get particular page
Page pdfPage = pageCollection[1];
```

Remember that this is zero-based indexing. So, if you want to access the first page, you need to index it as `1`.

## Step 5: Retrieve and Display Page Properties

Now we come to the exciting part — extracting the properties of the page! Each page has several properties like ArtBox, BleedBox, CropBox, MediaBox, and TrimBox that describe its dimensions and positioning. Let's access these properties and display them.

```csharp
// Get page properties
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", 
    pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, 
    pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", 
    pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, 
    pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", 
    pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, 
    pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", 
    pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, 
    pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", 
    pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, 
    pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", 
    pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, 
    pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);
```

This chunk of code does a few mighty things. It accesses each property related to the page's dimensions and orientation and then prints the information to the console. What you get is an overview of the page's properties that can aid in further modifications or analysis.

## Conclusion

And there you have it — a complete walkthrough on how to get PDF properties using Aspose.PDF for .NET! You now have the knowledge to extract vital information from PDF documents effortlessly. Whether you’re looking to analyze, report, or just log data from your PDFs, this robust library is a reliable ally. By mastering these steps, you're well on your way to becoming a PDF manipulation wizard! Don't hesitate to explore more features and functionalities that Aspose.PDF has to offer.

## FAQ's

### How can I install Aspose.PDF for .NET?  
You can install it via NuGet Package Manager in Visual Studio or download it directly from the Aspose website.

### Can I use Aspose.PDF for free?  
Yes, Aspose offers a free trial which you can get [here](https://releases.aspose.com/).

### Where can I find documentation for Aspose.PDF?  
You can refer to the documentation at [Aspose.pdf Documentation](https://reference.aspose.com/pdf/net/).

### How do I get support if I encounter issues?  
You can visit the Aspose forum for support where you can ask questions about your issues [here](https://forum.aspose.com/c/pdf/10).

### Is there a temporary license available?  
Yes, you can request a temporary license for evaluation by visiting [this link](https://purchase.aspose.com/temporary-license/).
