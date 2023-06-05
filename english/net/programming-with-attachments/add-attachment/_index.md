---
title: Add Attachment
linktitle: Add Attachment
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /net/programming-with-attachments/add-attachment/
---
### Sample source code for Add Attachment using Aspose.Words for .NET
 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Setup new file to be added as attachment
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Add attachment to document's attachment collection
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Save new output
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);
```