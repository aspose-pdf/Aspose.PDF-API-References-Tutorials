---
title: TeX to PDF
linktitle: TeX to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 290
url: /pdf/net/document-conversion/tex-to-pdf/
---



```csharp

            try
            {
                
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Instantiate Latex Load option object
                LatexLoadOptions Latexoptions = new LatexLoadOptions();
                // Create Document object
                Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "samplefile.tex", Latexoptions);
                // Save the output in PDF file
                doc.Save(dataDir + "TeXToPDF_out.pdf");
                
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        
```

