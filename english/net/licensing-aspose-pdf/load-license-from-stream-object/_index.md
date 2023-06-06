---
title: Load License From Stream Object
linktitle: Load License From Stream Object
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /net/licensing-aspose-pdf/load-license-from-stream-object/
---
### Sample source code for Load License From Stream Object using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Initialize license object
            Aspose.Pdf.License license = new Aspose.Pdf.License();
            // Load license in FileStream
            FileStream myStream = new FileStream("Aspose.Pdf.lic", FileMode.Open);
            // Set license
            license.SetLicense(myStream);
            Console.WriteLine("License set successfully.");
```