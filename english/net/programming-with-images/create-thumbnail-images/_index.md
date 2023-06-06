---
title: Create Thumbnail Images
linktitle: Create Thumbnail Images
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 100
url: /net/programming-with-images/create-thumbnail-images/
---
### Sample source code for Create Thumbnail Images using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Retrieve names of all the PDF files in a particular directory
            string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
            // Iterate through all the files entries in array
            for (int counter = 0; counter < fileEntries.Length; counter++)
            {
                //Open document
                Document pdfDocument = new Document(fileEntries[counter]);
                for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
                {
                    using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
                    {
                        //Create Resolution object
                        Resolution resolution = new Resolution(300);
                        //JpegDevice jpegDevice = new JpegDevice(500, 700, resolution, 100);
                        JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
                        //Convert a particular page and save the image to stream
                        jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
                        //Close stream
                        imageStream.Close();
                    }
                }
            }
            System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```