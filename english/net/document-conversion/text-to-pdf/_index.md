---
title: Text to PDF
linktitle: Text to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 300
url: /pdf/net/document-conversion/text-to-pdf/
---



```csharp

            try
            {
                
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";
                // Read the source text file
                TextReader tr = new StreamReader(dataDir + "log.txt");

                // Instantiate a Document object by calling its empty constructor
                Document doc = new Document();

                // Add a new page in Pages collection of Document
                Page page = doc.Pages.Add();

                // Create an instance of TextFragmet and pass the text from reader object to its constructor as argument
                TextFragment text = new TextFragment(tr.ReadToEnd());
                // Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

                // Add a new text paragraph in paragraphs collection and pass the TextFragment object
                page.Paragraphs.Add(text);

                // Save resultant PDF file
                doc.Save(dataDir + "TexttoPDF_out.pdf"); 
                
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        
```

