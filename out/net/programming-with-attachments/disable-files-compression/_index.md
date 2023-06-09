---
title: Disable Files Compression
linktitle: Disable Files Compression
second_title: Aspose.PDF for .NET API Reference
description: Learn how to disable file compression in a PDF file with Aspose.PDF for .NET. Step-by-step guide for easy handling.
type: docs
weight: 30
url: /content/net/programming-with-attachments/disable-files-compression/
---
In this tutorial, we will walk you through the following C# source code step by step to disable file compression in a PDF using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

### Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where the PDF file is located that you want to disable file compression. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Step 2: Open the existing PDF document

We open the existing PDF document using the specified path.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Step 3: Setting up the new file to add as an attachment

We configure the new file that we want to add as an attachment. In this example, we add a text file with the name "test_out.txt" and a description "Example text file".

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Step 4: Disable File Compression

We disable file compression by setting the Encoding property of the FileSpecification object to FileEncoding.None.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Step 5: Adding the attachment to the document's attachments collection

We add the attachment to the document's attachments collection.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Step 6: Save the new output file

Finally, we save the resulting new PDF file with the name "DisableFilesCompression_out.pdf" in the specified directory.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Sample source code for Disable Files Compression using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Setup new file to be added as attachment
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Specify Encoding proparty setting it to FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
// Add attachment to document's attachment collection
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Save new output
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Conclusion

In this tutorial, we explained how to disable file compression in a PDF using Aspose.PDF for .NET. You can now use this knowledge to maintain the integrity of attached files without compression.