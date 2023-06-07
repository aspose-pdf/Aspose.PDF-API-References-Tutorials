---
title: Custom Tab Stops
linktitle: Custom Tab Stops
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 120
url: /net/programming-with-text/custom-tab-stops/
---
### Sample source code for Custom Tab Stops using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document _pdfdocument = new Document();
            Page page = _pdfdocument.Pages.Add();
            Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
            Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
            ts1.AlignmentType = TabAlignmentType.Right;
            ts1.LeaderType = TabLeaderType.Solid;
            Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
            ts2.AlignmentType = TabAlignmentType.Center;
            ts2.LeaderType = TabLeaderType.Dash;
            Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
            ts3.AlignmentType = TabAlignmentType.Left;
            ts3.LeaderType = TabLeaderType.Dot;
            TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
            TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
            TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
            TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
            text2.Segments.Add(new TextSegment("#$TAB"));
            text2.Segments.Add(new TextSegment("data22 "));
            text2.Segments.Add(new TextSegment("#$TAB"));
            text2.Segments.Add(new TextSegment("data23"));
            page.Paragraphs.Add(header);
            page.Paragraphs.Add(text0);
            page.Paragraphs.Add(text1);
            page.Paragraphs.Add(text2);
            dataDir = dataDir + "CustomTabStops_out.pdf";
            _pdfdocument.Save(dataDir);
            Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```