---
title: Add Date Time Stamp
linktitle: Add Date Time Stamp
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
### Sample source code for Add Date Time Stamp using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
            string annotationText = string.Empty;
            annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
            // Create text stamp
            TextStamp textStamp = new TextStamp(annotationText);
            // Set properties of the stamp
            textStamp.BottomMargin = 10;
            textStamp.RightMargin = 20;
            textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
            textStamp.VerticalAlignment = VerticalAlignment.Bottom;
            // Adding stamp on stamp collection
            pdfDocument.Pages[1].AddStamp(textStamp);
            DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
            FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
            textAnnotation.Name = "Stamp";
            textAnnotation.Accept(new AnnotationSelector(textAnnotation));
            textAnnotation.Contents = textStamp.Value;
            // TextAnnotation.Open = true;
            // TextAnnotation.Icon = Aspose.Pdf.InteractiveFeatures.Annotations.TextIcon.Key;
            Border border = new Border(textAnnotation);
            border.Width = 0;
            border.Dash = new Dash(1, 1);
            textAnnotation.Border = border;
            textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
            pdfDocument.Pages[1].Annotations.Add(textAnnotation);
            dataDir = dataDir + "AddDateTimeStamp_out.pdf";
            // Save output document
            pdfDocument.Save(dataDir);
            Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);            
```