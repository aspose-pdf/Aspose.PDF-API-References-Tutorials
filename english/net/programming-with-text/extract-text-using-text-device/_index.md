---
title: Extract Text Using Text Device
linktitle: Extract Text Using Text Device
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 210
url: /net/programming-with-text/extract-text-using-text-device/
---
### Sample source code for Extract Text Using Text Device using Aspose.PDF for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Open document
            Document pdfDocument = new Document( dataDir + "input.pdf");
            System.Text.StringBuilder builder = new System.Text.StringBuilder();
            // String to hold extracted text
            string extractedText = "";
            foreach (Page pdfPage in pdfDocument.Pages)
            {
                using (MemoryStream textStream = new MemoryStream())
                {
                    // Create text device
                    TextDevice textDevice = new TextDevice();
                    // Set text extraction options - set text extraction mode (Raw or Pure)
                    TextExtractionOptions textExtOptions = new
                    TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
                    textDevice.ExtractionOptions = textExtOptions;
                    // Convert a particular page and save text to the stream
                    textDevice.Process(pdfPage, textStream);
                    // Convert a particular page and save text to the stream
                    textDevice.Process(pdfDocument.Pages[1], textStream);
                    // Close memory stream
                    textStream.Close();
                    // Get text from memory stream
                    extractedText = Encoding.Unicode.GetString(textStream.ToArray());
                }
                builder.Append(extractedText);
            }
            dataDir = dataDir + "input_Text_Extracted_out.txt";
            // Save the extracted text in text file
            File.WriteAllText(dataDir, builder.ToString());
            Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```