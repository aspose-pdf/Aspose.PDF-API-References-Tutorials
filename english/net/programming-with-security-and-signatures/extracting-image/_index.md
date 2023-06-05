---
title: Extracting Image
linktitle: Extracting Image
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 70
url: /net/programming-with-security-and-signatures/extracting-image/
---
### Sample source code for Extracting Image using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
            string input = dataDir+ @"ExtractingImage.pdf";
            using (Document pdfDocument = new Document(input))
            {
                foreach (Field field in pdfDocument.Form)
                {
                    SignatureField sf = field as SignatureField;
                    if (sf != null)
                    {
                        string outFile = dataDir+ @"output_out.jpg";
                        using (Stream imageStream = sf.ExtractImage())
                        {
                            if (imageStream != null)
                            {
                                using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
                                {
                                    image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
                                }
                            }
                        }
                    }
                }
            }
```