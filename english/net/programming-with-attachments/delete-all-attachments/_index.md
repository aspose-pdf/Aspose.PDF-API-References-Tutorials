---
title: Delete All Attachments
linktitle: Delete All Attachments
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /net/programming-with-attachments/delete-all-attachments/
---
### Sample source code for Delete All Attachments using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Attachments();
            // Open document
            Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
            // Delete all attachments
            pdfDocument.EmbeddedFiles.Delete();
            dataDir = dataDir + "DeleteAllAttachments_out.pdf";
            // Save updated file
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);
```