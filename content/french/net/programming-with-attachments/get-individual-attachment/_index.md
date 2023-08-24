---
title: Get Individual Attachment In PDF File
linktitle: Get Individual Attachment In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to get an individual attachment in PDF file with Aspose.PDF for .NET. 
type: docs
weight: 60
url: /fr/net/programming-with-attachments/get-individual-attachment/
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

### FAQs for get individual attachment in PDF file

#### Q: What is the purpose of getting an individual attachment from a PDF document?

A: Getting an individual attachment allows you to extract and save a specific embedded file within a PDF, which can be useful for further analysis or manipulation.

#### Q: How can I benefit from this tutorial in my PDF-related tasks?

A: This tutorial provides step-by-step instructions and C# source code to retrieve and save a particular attachment from a PDF document using Aspose.PDF for .NET.

#### Q: What attachment properties can I access using this tutorial?

A: You can access attachment properties such as name, description, MIME type, control hash, creation date, modification date, and size of the specific attachment.

#### Q: Can I modify the code to get attachments other than the first attachment?

A: Absolutely, you can adjust the index (e.g., `pdfDocument.EmbeddedFiles[1]`) to retrieve attachments at different indices within the PDF.

#### Q: How do I save the retrieved attachment to a file?

A: This tutorial provides code to retrieve the attachment's content and save it to a text file with a specified name.

#### Q: What is the significance of the "Check Hash" property in attachment information?

A: The "Check Hash" property represents the control hash value of the attachment, which can be used to verify the integrity of the attachment.

#### Q: Can I extend this knowledge to extract attachments with specific criteria, such as file type?

A: Yes, you can enhance the code to filter attachments based on specific criteria such as file type or other properties.

#### Q: How does Aspose.PDF for .NET simplify the process of extracting individual attachments?

A: Aspose.PDF for .NET provides a user-friendly API that facilitates the extraction and manipulation of attachments within PDF documents.

#### Q: Is this tutorial relevant for password-protected PDF files as well?

A: Yes, you can adapt similar techniques to retrieve individual attachments from password-protected PDF files using Aspose.PDF for .NET.
