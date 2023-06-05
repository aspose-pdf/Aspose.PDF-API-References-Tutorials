---
title: Is Password Protected
linktitle: Is Password Protected
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 90
url: /net/programming-with-security-and-signatures/is-password-protected/
---
### Sample source code for Is Password Protected using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
            // Load the source PDF doucment
            PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
            // Determine that source PDF file is Encrypted with password
            bool encrypted = fileInfo.IsEncrypted;
            // MessageBox displays the current status related to PDf encryption
           Console.WriteLine(encrypted.ToString());
```