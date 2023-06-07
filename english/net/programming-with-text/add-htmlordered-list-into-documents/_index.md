---
title: Add HTMLOrdered List Into Documents
linktitle: Add HTMLOrdered List Into Documents
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 30
url: /net/programming-with-text/add-htmlordered-list-into-documents/
---
### Sample source code for Add HTMLOrdered List Into Documents using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // The path to the output document.  
            string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
            // Instantiate Document object  
            Document doc = new Document();
            // Instantiate HtmlFragment object with corresponding HTML fragment  
            HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
            // Add Page in Pages Collection  
            Page page = doc.Pages.Add();
            // Add HtmlFragment inside page  
            page.Paragraphs.Add(t);
            // Save resultant PDF file  
            doc.Save(outFile);
```