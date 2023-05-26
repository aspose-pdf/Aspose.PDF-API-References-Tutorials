---
title: Get File Info
linktitle: Get File Info
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use the GetFileInfo feature of Aspose.PDF for .NET to retrieve metadata information about a PDF document.
type: docs
weight: 180
url: /net/programming-with-document/getfileinfo/
---

Aspose.PDF for .NET is a popular PDF manipulation library that enables developers to create, edit, and convert PDF files in their .NET applications. One of the features offered by this library is the ability to retrieve information about a PDF document's metadata. This tutorial will guide you through the steps of using the `GetFileInfo` feature of Aspose.PDF for .NET to retrieve information about a PDF document's metadata.

## Step 1: Install Aspose.PDF for .NET

To use Aspose.PDF for .NET in your .NET applications, you must first install the library. You can download the latest version of the library from the [Aspose.PDF for .NET download page](https://releases.aspose.com/pdf/net).

Once you have downloaded the library, extract the contents of the ZIP file to a folder on your computer. You will then need to add a reference to the Aspose.PDF for .NET DLL in your .NET project.

## Step 2: Load the PDF Document

Once you have installed Aspose.PDF for .NET and added a reference to the DLL in your .NET project, you can begin using the `GetFileInfo` feature to retrieve information about a PDF document's metadata.

The first step in using this feature is to load the PDF document that you want to retrieve information about. To do this, you can use the following code:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

In the above code, replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your PDF document is located. This code will load the PDF document into a `Document` object, which you can then use to retrieve information about the document's metadata.

## Step 3: Retrieve the Document's Metadata

To retrieve information about a PDF document's metadata, you can use the following code:

```csharp
// Get document information
DocumentInfo docInfo = pdfDocument.Info;

// Show document information
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

In the above code, each line retrieves a different metadata property of the PDF document and outputs it to the console. You can customize this code to retrieve only the properties that you are interested in.

### Example source code get PDF file info using Aspose.PDF for .NET

Here is the full source code for retrieving a PDF document's metadata using the `GetFileInfo` feature of Aspose.PDF for .NET:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Get document information
DocumentInfo docInfo = pdfDocument.Info;

// Show document information
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```
