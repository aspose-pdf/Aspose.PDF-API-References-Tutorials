---
title: Replace Missing Fonts
linktitle: Replace Missing Fonts
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 260
url: /pdf/net/document-conversion/replace-missing-fonts/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            Aspose.Pdf.Text.Font originalFont = null;
            try
            {
                originalFont = FontRepository.FindFont("AgencyFB");
            }
            catch (Exception)
            {
                // Font is missing on destination machine
                FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
            }
            var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
            var pdf = new Document(dataDir + "input.pdf");
            pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
            pdf.Save(fileNew.FullName);
            
        
```

