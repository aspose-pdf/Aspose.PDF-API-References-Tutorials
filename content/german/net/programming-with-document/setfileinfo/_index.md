---
title: Set File Info In PDF File
linktitle: Set File Info In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to set file info in PDF file with this step-by-step guide.
type: docs
weight: 310
url: /de/net/programming-with-document/setfileinfo/
---
If you are working on a project that requires managing PDF files using Aspose.PDF for .NET, one of the features you may want to utilize is the ability to set file information for a PDF document. The file information includes various details such as the author, creation date, keywords, modification date, subject, and title. This guide will walk you through the process of setting file information for a PDF document using C# source code with Aspose.PDF for .NET.

## Step-by-step guide for setting file info using Aspose.PDF for .NET

1. Create a new C# project in your Visual Studio IDE.
2. Add a reference to the Aspose.PDF for .NET library in your project.
3. Create a new PDF document object by providing the path to the PDF file you want to modify the file information for.

## Step 1: Set path to the documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF document

```csharp
// Open document
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Step 3: Use the DocumentInfo object to access the file information of the PDF document.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Step 4: Set the desired file information values using the properties of the DocumentInfo object.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Step 5: Save the updated PDF document to the specified location.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Step 6: Verify that the file information has been successfully updated.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

You have successfully set file information for a PDF document using Aspose.PDF for .NET.

### Example source code for Set File Info using Aspose.PDF for .NET


```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Specify document information
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Save output document
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Conclusion

In conclusion, Aspose.PDF for .NET provides a simple and effective way of setting file information for PDF documents. By following the above-mentioned steps, you can easily set the desired file information values for your PDF documents using C# source code.

### FAQ's for set file info in PDF file

#### Q: Can I set additional file information properties not mentioned in the example?

A: Yes, you can set additional file information properties using the `DocumentInfo` object in Aspose.PDF for .NET. The `DocumentInfo` class provides various properties that allow you to set additional information such as the producer, version, and custom properties.

#### Q: Is it possible to retrieve the file information from an existing PDF document?

A: Yes, you can retrieve the file information from an existing PDF document using Aspose.PDF for .NET. To do this, you can use the `DocumentInfo` object to access the file information properties and read the information stored in the PDF document.

#### Q: Does setting the file information modify the original PDF document?

A: No, setting the file information using Aspose.PDF for .NET does not modify the original PDF document. Instead, it creates a new PDF document with the updated file information. The original PDF document remains unchanged.