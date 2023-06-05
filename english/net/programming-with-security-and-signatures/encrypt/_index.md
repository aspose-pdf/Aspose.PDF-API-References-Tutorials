---
title: Encrypt
linktitle: Encrypt
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 60
url: /net/programming-with-security-and-signatures/encrypt/
---
### Sample source code for Encrypt using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
            // Open document
            Document document = new Document(dataDir+ "Encrypt.pdf");
            // Encrypt PDF
            document.Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
            dataDir = dataDir + "Encrypt_out.pdf";
            // Save updated PDF
            document.Save(dataDir);
            Console.WriteLine("\nPDF file encrypted successfully.\nFile saved at " + dataDir);
```