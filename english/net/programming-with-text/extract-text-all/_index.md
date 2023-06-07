---
title: Extract Text All
linktitle: Extract Text All
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 180
url: /net/programming-with-text/extract-text-all/
---
### Sample source code for Extract Text All using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
            // Create TextAbsorber object to extract text
            TextAbsorber textAbsorber = new TextAbsorber();
            // Accept the absorber for all the pages
            pdfDocument.Pages.Accept(textAbsorber);
            // Get the extracted text
            string extractedText = textAbsorber.Text;
            // Create a writer and open the file
            TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
            // Write a line of text to the file
            tw.WriteLine(extractedText);
            // Close the stream
            tw.Close();
```