---
title: Get XMP Metadata
linktitle: Get XMP Metadata
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use the GetXmpMetadata feature of Aspose.PDF for .NET to extract XMP metadata from a PDF document using C# source code.
type: docs
weight: 200
url: /tr/net/programming-with-document/getxmpmetadata/
---
Aspose.PDF for .NET is a popular PDF manipulation library that enables developers to create, edit, and convert PDF files in their .NET applications. One of the features offered by this library is the ability to extract XMP metadata from a PDF document. This tutorial will guide you through the steps of using the `GetXmpMetadata` feature of Aspose.PDF for .NET to extract XMP metadata from a PDF document.

## Step 1: Install Aspose.PDF for .NET

To use Aspose.PDF for .NET in your .NET applications, you must first install the library. You can download the latest version of the library from the [Aspose.PDF for .NET download page](https://releases.aspose.com/pdf/net).

Once you have downloaded the library, extract the contents of the ZIP file to a folder on your computer. You will then need to add a reference to the Aspose.PDF for .NET DLL in your .NET project.

## Step 2: Load the PDF Document

Once you have installed Aspose.PDF for .NET and added a reference to the DLL in your .NET project, you can begin using the `GetXmpMetadata` feature to extract XMP metadata from a PDF document.

The first step in using this feature is to load the PDF document that you want to extract XMP metadata from. To do this, you can use the following code:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

In the above code, replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your PDF document is located. This code will load the PDF document into a `Document` object, which you can then use to extract XMP metadata.

## Step 3: Extract XMP Metadata

To extract XMP metadata from a PDF document, you can use the following code:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

In the above code, `xmp:CreateDate`, `xmp:Nickname`, and `xmp:CustomProperty` are examples of XMP metadata properties that you can extract from a PDF document. You can replace these property names with the names of any other XMP metadata properties that you want to extract.

### Example Source Code for Get XMP Metadata using Aspose.PDF for .NET

Here is the full source code for extracting XMP metadata from a PDF document using the `GetXmpMetadata` feature of Aspose.PDF for .NET:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Extract XMP metadata
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

In the above code, replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your PDF document is located. This code will extract XMP metadata from the PDF document and output it to the console.

## Conclusion

In this tutorial, we have discussed how to use Aspose.PDF for .NET to extract XMP metadata from a PDF document. XMP metadata provides valuable information about a document, and Aspose.PDF for .NET allows developers to access this information and use it in their applications as needed. By extracting XMP metadata, developers can gain insights into a document's creation date, author, and other descriptive data. This information can be used to enhance the functionality and user experience of PDF applications. Aspose.PDF for .NET provides a simple and straightforward API to access XMP metadata, making it easy to integrate this feature into .NET applications.

### FAQ's

#### Q: What is XMP metadata in a PDF document?

A: XMP metadata in a PDF document refers to Extensible Metadata Platform (XMP) information that is embedded within the document. XMP metadata provides a standard way to store information about the document, such as author, creation date, keywords, and other descriptive data. It allows for easy retrieval and exchange of metadata across different systems and applications.

#### Q: What type of information can be extracted using the GetXmpMetadata feature?

A: The GetXmpMetadata feature allows developers to extract various XMP metadata properties from a PDF document. Some examples of XMP metadata properties that can be extracted are `xmp:CreateDate`, `xmp:Nickname`, and `xmp:CustomProperty`. Developers can access these properties and use them in their applications as needed.

#### Q: Can I extract custom XMP metadata properties using Aspose.PDF for .NET?

A: Yes, you can extract custom XMP metadata properties using Aspose.PDF for .NET. Custom XMP metadata properties can be included in a PDF document to store additional information specific to your application or requirements. You can extract and use these custom properties as needed.

#### Q: Is Aspose.PDF for .NET capable of extracting other metadata information from a PDF document?

A: Yes, Aspose.PDF for .NET provides various features to extract metadata information from a PDF document. Apart from XMP metadata, you can also extract information like Document Information (title, author, subject, keywords), PDF version, encryption details, and more.