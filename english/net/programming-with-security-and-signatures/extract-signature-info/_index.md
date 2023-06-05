---
title: Extract Signature Info
linktitle: Extract Signature Info
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 80
url: /net/programming-with-security-and-signatures/extract-signature-info/
---
### Sample source code for Extract Signature Info using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
                string input = dataDir + "ExtractSignatureInfo.pdf";
                using (Document pdfDocument = new Document(input))
                {
                    foreach (Field field in pdfDocument.Form)
                    {
                        SignatureField sf = field as SignatureField;
                        if (sf != null)
                        {
                            Stream cerStream = sf.ExtractCertificate();
                            if (cerStream != null)
                            {
                                using (cerStream)
                                {
                                    byte[] bytes = new byte[cerStream.Length];
                                    using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                                    {
                                        cerStream.Read(bytes, 0, bytes.Length);
                                        fs.Write(bytes, 0, bytes.Length);
                                    }
                                }
                            }
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
```