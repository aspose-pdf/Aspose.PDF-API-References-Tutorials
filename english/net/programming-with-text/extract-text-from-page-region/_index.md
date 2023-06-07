---
title: Extract Text From Page Region
linktitle: Extract Text From Page Region
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 190
url: /net/programming-with-text/extract-text-from-page-region/
---
### Sample source code for Extract Text From Page Region using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
            // Create TextAbsorber object to extract text
            TextAbsorber absorber = new TextAbsorber();
            absorber.TextSearchOptions.LimitToPageBounds = true;
            absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
            // Accept the absorber for first page
            pdfDocument.Pages[1].Accept(absorber);
            // Get the extracted text
            string extractedText = absorber.Text;
            // Create a writer and open the file
            TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
            // Write a line of text to the file
            tw.WriteLine(extractedText);
            // Close the stream
            tw.Close();
```