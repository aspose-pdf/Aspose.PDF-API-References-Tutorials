---
title: Secure License
linktitle: Secure License
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 40
url: /net/licensing-aspose-pdf/secure-license/
---
### Sample source code for Secure License using Aspose.Words for .NET 
```csharp
            using (Stream zip = new SecureLicense().GetType().Assembly.GetManifestResourceStream("Aspose.Total.lic.zip"))
            {
                using (ZipFile zf = ZipFile.Read(zip))
                {
                    MemoryStream ms = new MemoryStream();
                    ZipEntry e = zf["Aspose.Total.lic"];
                    e.ExtractWithPassword(ms, "test");
                    ms.Position = 0;
                }
            }
```