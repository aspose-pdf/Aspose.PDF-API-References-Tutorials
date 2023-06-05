---
title: Get Attachment Info
linktitle: Get Attachment Info
second_title: Aspose.PDF for .NET API Reference
description: Learn how to get information about a specific attachment in a PDF file with Aspose.PDF for .NET. Step by step guide.
type: docs
weight: 50
url: /net/programming-with-attachments/get-attachment-info/
---
In this tutorial, we will walk you through the following C# source code step by step to get the information about a specific attachment of a PDF file using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

### Step 1: Document Directory Setup

In the source code provided, you need to specify the directory where the PDF file is located from which you want to get the attachment information. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Step 2: Open the existing PDF document

We open the existing PDF document using the specified path.

```csharp
Document pdfDocument = new Document(dataDir + "GetAttachmentInfo.pdf");
```

### Step 3: Obtaining a Specific Attachment

We retrieve a specific attachment from the document's attachments collection. In this example, we get the first attachment using index 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Step 4: Get File Properties

We display attachment properties such as name, description, MIME type, control hash, date created, date modified, and size.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Check if object parameters contain additional information
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Sample source code for Get Attachment Info using Aspose.Words for .NET
 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetAttachmentInfo.pdf");
// Get particular embedded file
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Get the file properties
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
// Check if parameter object contains the parameters
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

```

## Conclusion

In this tutorial, we explained how to get the information about a specific attachment of a PDF file using Aspose.PDF for .NET. You can now use this knowledge to extract and view attachment information from your PDF files.

