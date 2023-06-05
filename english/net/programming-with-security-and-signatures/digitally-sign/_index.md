---
title: Digitally Sign
linktitle: Digitally Sign
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 40
url: /net/programming-with-security-and-signatures/digitally-sign/
---
### Sample source code for Digitally Sign using Aspose.Words for .NET 
```csharp
            try
            {
                // The path to the documents directory.
                string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
                string pbxFile = "";
                string inFile = dataDir + @"DigitallySign.pdf";
                string outFile = dataDir + @"DigitallySign_out.pdf";
                using (Document document = new Document(inFile))
                {
                    using (PdfFileSignature signature = new PdfFileSignature(document))
                    {
                        PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Use PKCS7/PKCS7Detached objects
                        DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
                        System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
                        // Set signature appearance
                        signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
                        // Create any of the three signature types
                        signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
                        // Save output PDF file
                        signature.Save(outFile);
                    }
                }
                using (Document document = new Document(outFile))
                {
                    using (PdfFileSignature signature = new PdfFileSignature(document))
                    {
                        IList<string> sigNames = signature.GetSignNames();
                        if (sigNames.Count > 0) // Any signatures?
                        {
                            if (signature.VerifySigned(sigNames[0] as string)) // Verify first one
                            {
                                if (signature.IsCertified) // Certified?
                                {
                                    if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Get access permission
                                    {
                                        // Do something
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