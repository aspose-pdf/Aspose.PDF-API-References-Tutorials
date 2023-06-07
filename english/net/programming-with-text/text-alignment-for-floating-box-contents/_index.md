---
title: Text Alignment For Floating Box Contents
linktitle: Text Alignment For Floating Box Contents
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 520
url: /net/programming-with-text/text-alignment-for-floating-box-contents/
---
### Sample source code for Text Alignment For Floating Box Contents using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Aspose.Pdf.Document doc = new Document();
            doc.Pages.Add();
            Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
            floatBox.VerticalAlignment = VerticalAlignment.Bottom;
            floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
            floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
            floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
            doc.Pages[1].Paragraphs.Add(floatBox);
            Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
            floatBox1.VerticalAlignment = VerticalAlignment.Center;
            floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
            floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
            floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
            doc.Pages[1].Paragraphs.Add(floatBox1);
            Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
            floatBox2.VerticalAlignment = VerticalAlignment.Top;
            floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
            floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
            floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
            doc.Pages[1].Paragraphs.Add(floatBox2);
            doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```