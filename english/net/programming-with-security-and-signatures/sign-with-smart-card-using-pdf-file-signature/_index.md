---
title: Sign With Smart Card Using Pdf File Signature
linktitle: Sign With Smart Card Using Pdf File Signature
second_title: Aspose.PDF for .NET API Reference
description: Sign your PDF files securely with a smart card using Aspose.PDF for .NET.
type: docs
weight: 110
url: /net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---

Digital signing with a smart card is a secure way to sign PDF files. With Aspose.PDF for .NET, you can easily sign a PDF file using a smart card by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here are the necessary import directives:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to sign. Replace `"YOUR DOCUMENTS DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 3: Load the PDF document

Now we will load the PDF document to be signed using the following code:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Step 4: Perform the signature with the smart card

In this step, we will perform the signature with the smart card using the `PdfFileSignature` class from the `Facades` library. We select the smart card certificate from the Windows certificate store and specify the necessary signing information. Here is the corresponding code:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Select the certificate in the store
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Step 5: Verify Signature

Finally, we verify the signature of the signed PDF file using the `PdfFileSignature` class. We get the signature names and check them one by one. If a signature fails verification, an exception is thrown. Here is the corresponding code:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Sample source code for Sign With Smart Card Using Pdf File Signature using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Sign with certificate selection in the windows certificate store
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Manually chose the certificate in the store
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

## Conclusion

Congratulation! You now have a step-by-step guide to signing a PDF file with a smart card using Aspose.PDF for .NET. You can use this code to add secure digital signatures to your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced digital signature and certificate management features.
