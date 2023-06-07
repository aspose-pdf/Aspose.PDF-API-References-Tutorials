---
title: Extract Text Page
linktitle: Extract Text Page
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 200
url: /net/programming-with-text/extract-text-page/
---
### Sample source code for Extract Text Page using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
            // Create TextAbsorber object to extract text
            TextAbsorber textAbsorber = new TextAbsorber();
            // Accept the absorber for a particular page
            pdfDocument.Pages[1].Accept(textAbsorber);
            // Get the extracted text
            string extractedText = textAbsorber.Text;
            dataDir = dataDir + "extracted-text_out.txt";
            // Create a writer and open the file
            TextWriter tw = new StreamWriter(dataDir);
            // Write a line of text to the file
            tw.WriteLine(extractedText);
            // Close the stream
            tw.Close();
            Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```