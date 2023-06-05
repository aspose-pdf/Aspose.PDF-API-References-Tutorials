---
title: Decrypt
linktitle: Decrypt
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 20
url: /net/programming-with-security-and-signatures/decrypt/
---
### Sample source code for Decrypt using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
            // Open document
            Document document = new Document(dataDir+ "Decrypt.pdf", "password");
            // Decrypt PDF
            document.Decrypt();
            dataDir = dataDir + "Decrypt_out.pdf";
            // Save updated PDF
            document.Save(dataDir);
            Console.WriteLine("\nPDF file decrypted successfully.\nFile saved at " + dataDir);
```