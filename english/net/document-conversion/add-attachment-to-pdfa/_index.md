---
title: Add Attachment to PDFA
linktitle: Add Attachment to PDFA
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /pdf/net/document-conversion/add-attachment-to-pdfa/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Instantiate Document instance to load existing file
            Aspose.Pdf.Document doc = new Document(dataDir + "input.pdf");
            // Setup new file to be added as attachment
            FileSpecification fileSpecification = new FileSpecification(dataDir + "aspose-logo.jpg", "Large Image file");
            // Add attachment to document's attachment collection
            doc.EmbeddedFiles.Add(fileSpecification);
            // Perform conversion to PDF/A_3a so attachment is included in resultnat file
            doc.Convert(dataDir + "log.txt", Aspose.Pdf.PdfFormat.PDF_A_3A, ConvertErrorAction.Delete);
            // Save resultant file
            doc.Save(dataDir + "AddAttachmentToPDFA_out.pdf");
            
            Console.WriteLine("\nAttachment added successfully to PDF/A file.\nFile saved at " + dataDir);
        
```

