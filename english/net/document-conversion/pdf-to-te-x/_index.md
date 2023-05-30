---
title: PDF to Te X
linktitle: PDF to Te X
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 190
url: /pdf/net/document-conversion/pdf-to-te-x/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Create Document object
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PDFToTeX.pdf");

            // Instantiate LaTex save option            
            LaTeXSaveOptions saveOptions = new LaTeXSaveOptions();

            // Specify the output directory 
            string pathToOutputDirectory = dataDir;

            // Set the output directory path for save option object
            saveOptions.OutDirectoryPath = pathToOutputDirectory;

            // Save PDF file into LaTex format            
            doc.Save(dataDir + "PDFToTeX_out.tex", saveOptions);
            
        
```

