---
title: Style Text Structure
linktitle: Style Text Structure
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 190
url: /net/programming-with-tagged-pdf/style-text-structure/
---
### Sample source code for Style Text Structure using Aspose.PDF for .NET 
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
            ParagraphElement p = taggedContent.CreateParagraphElement();
            taggedContent.RootElement.AppendChild(p);
            // Under Development
            p.StructureTextState.FontSize = 18F;
            p.StructureTextState.ForegroundColor = Color.Red;
            p.StructureTextState.FontStyle = FontStyles.Italic;
            p.SetText("Red italic text.");
            // Save Tagged Pdf Document
            document.Save(dataDir + "StyleTextStructure.pdf");
```