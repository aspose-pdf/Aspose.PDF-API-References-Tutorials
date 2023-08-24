---
title: Get All The Attachments In PDF File
linktitle: Get All The Attachments In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to get all attachments in PDF file with Aspose.PDF for .NET. Step-by-step guide for easy handling.
type: docs
weight: 40
url: /zh/net/programming-with-attachments/get-all-the-attachments/
---
In this tutorial, we will walk you through the following C# source code step by step to get all attachments in PDF file using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

### Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where the PDF file is located from which you want to get the attachments. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Step 2: Open the existing PDF document

We open the existing PDF document using the specified path.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Step 3: Obtaining the Attachments Collection

We get the collection of attachments from the document.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Step 4: Retrieving attachments

We go through the collection to get all the attachments and display their information. We also save attachments in individual files.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Check if object parameters contain additional information
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Retrieve the attachment and save in a file
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Sample source code for Get Allthe Attachments using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Get embedded files collection
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Get count of the embedded files
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Loop through the collection to get all the attachments
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Conclusion

In this tutorial, we explained how to get all attachments from a PDF file using Aspose.PDF for .NET. You can now use this knowledge to extract and manipulate attachments from your PDF files.

## FAQ's for get all the attachments in PDF file

#### Q: Why would I need to retrieve all attachments from a PDF document?

A: Retrieving attachments allows you to access and manipulate additional files embedded within a PDF, which can be useful for archiving, sharing, or further processing.

#### Q: What types of files can be attached to a PDF document?

A: PDF documents can contain a wide range of attached files, including images, documents, spreadsheets, audio files, and more.

#### Q: How does this tutorial help me retrieve attachments from a PDF using Aspose.PDF for .NET?

A: This tutorial provides step-by-step instructions and C# source code to access and retrieve all attachments within a PDF document.

#### Q: Can I retrieve specific attachments instead of all attachments using this tutorial?

A: Yes, you can modify the provided code to selectively retrieve attachments based on your requirements.

#### Q: What information about each attachment can I obtain using this tutorial?

A: This tutorial demonstrates how to retrieve and display details such as the attachment's name, description, MIME type, creation date, modification date, and size.

#### Q: How are the retrieved attachments saved using this tutorial?

A: The tutorial guides you through saving each retrieved attachment as a separate file in the specified directory.

#### Q: Can I use this knowledge to extract attachments from password-protected PDF files?

A: Yes, you can apply similar principles to retrieve attachments from password-protected PDF files using Aspose.PDF for .NET.

#### Q: How does Aspose.PDF for .NET facilitate attachment retrieval?

A: Aspose.PDF for .NET provides an intuitive API that allows you to access and manipulate attachments in PDF documents easily.

#### Q: Are there specific scenarios where retrieving attachments is recommended?

A: Retrieving attachments is useful when you need to access files embedded within a PDF, such as extracting images, audio files, or additional documents.