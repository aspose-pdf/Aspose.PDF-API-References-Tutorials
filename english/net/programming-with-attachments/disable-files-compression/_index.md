---
title: Disable Files Compression
linktitle: Disable Files Compression
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /net/programming-with-attachments/disable-files-compression/
---
### Sample source code for Disable Files Compression using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Attachments();
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