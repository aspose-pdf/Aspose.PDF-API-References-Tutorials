---
title: Get Individual Attachment
linktitle: Get Individual Attachment
second_title: Aspose.PDF for .NET API Reference
description: Learn how to get an individual attachment in a PDF file with Aspose.PDF for .NET. 
type: docs
weight: 60
url: /content/net/programming-with-attachments/get-individual-attachment/
---
In this tutorial, we will walk you through the following C# source code step by step to get an individual attachment of a PDF file using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

### Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where the PDF file is located from which you want to get the individual attachment. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Step 2: Open the existing PDF document

We open the existing PDF document using the specified path.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
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

### Step 5: Retrieve attachment and save to file

We retrieve the content of the attachment and save it to a text file. In this example, the file is saved with the name "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Sample source code for Get Individual Attachment using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
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
// Get the attachment and write to file or stream
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Conclusion

In this tutorial, we explained how to get an individual attachment from a PDF file using Aspose.PDF for .NET. You can now use this knowledge to extract and save attachments from your PDF files.
