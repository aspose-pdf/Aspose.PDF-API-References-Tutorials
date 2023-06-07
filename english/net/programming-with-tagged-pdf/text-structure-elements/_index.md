---
title: Text Structure Elements
linktitle: Text Structure Elements
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 230
url: /net/programming-with-tagged-pdf/text-structure-elements/
---
### Sample source code for Text Structure Elements using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Create Pdf Document
            Document document = new Document();
            // Get Content for work with TaggedPdf
            ITaggedContent taggedContent = document.TaggedContent;
            // Set Title and Language for Documnet
            taggedContent.SetTitle("Tagged Pdf Document");
            taggedContent.SetLanguage("en-US");
            // Get Root Structure Elements
            StructureElement rootElement = taggedContent.RootElement;
            ParagraphElement p = taggedContent.CreateParagraphElement();
            // Set Text to Text Structure Element
            p.SetText("Paragraph.");
            rootElement.AppendChild(p);
            // Save Tagged Pdf Document
            document.Save(dataDir + "TextStructureElement.pdf");
```