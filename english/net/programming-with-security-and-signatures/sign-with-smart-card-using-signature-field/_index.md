---
title: Sign With Smart Card Using Signature Field
linktitle: Sign With Smart Card Using Signature Field
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 120
url: /net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
### Sample source code for Sign With Smart Card Using Signature Field using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
            File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
            using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
            {
                using (Document doc = new Document(fs))
                {
                    SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
                    // Sign with certificate selection in the windows certificate store
                    System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
                    store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
                    // Manually chose the certificate in the store
                    System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
                    Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
                    {
                        Authority = "Me",
                        Reason = "Reason",
                        ContactInfo = "Contact"
                    };
                    field1.PartialName = "sig1";
                    doc.Form.Add(field1, 1);
                    field1.Sign(externalSignature);
                    doc.Save();
                }
            }
            using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
            {
                IList<string> sigNames = pdfSign.GetSignNames();
                for (int index = 0; index <= sigNames.Count - 1; index++)
                {
                    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
                    {
                        throw new ApplicationException("Not verified");
                    }
                }
            }
```