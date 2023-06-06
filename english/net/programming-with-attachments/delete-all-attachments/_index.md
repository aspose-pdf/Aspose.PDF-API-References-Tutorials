---
title: Delete All Attachments
linktitle: Delete All Attachments
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove all attachments from a PDF file using Aspose.PDF for .NET. Step-by-step guide for easy handling.
type: docs
weight: 20
url: /net/programming-with-attachments/delete-all-attachments/
---
In this tutorial, we will walk you through the following C# source code step by step to remove all attachments from a PDF file using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

### Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where the PDF file is located from which you want to remove the attachments. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Step 2: Open the existing PDF document

We open the existing PDF document using the specified path.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### Step 3: Remove all attachments

We remove all attachments from the document.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### Step 4: Save the Updated File

Finally, we save the updated PDF file with the name "DeleteAllAttachments_out.pdf" in the specified directory.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### Sample source code for Delete All Attachments using Aspose.PDF for .NET 

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// Delete all attachments
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// Save updated file
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## Conclusion

In this tutorial, we have explained how to remove all attachments from a PDF file using Aspose.PDF for .NET. You can now use this knowledge to clean up your PDF documents by removing all unwanted attachments.

