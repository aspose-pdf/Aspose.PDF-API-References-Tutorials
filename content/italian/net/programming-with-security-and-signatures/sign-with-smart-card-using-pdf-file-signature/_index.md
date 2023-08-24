---
title: Sign With Smart Card Using PDF File Signature
linktitle: Sign With Smart Card Using PDF File Signature
second_title: Aspose.PDF for .NET API Reference
description: Sign your PDF files securely with a smart card using Aspose.PDF for .NET.
type: docs
weight: 110
url: /it/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
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

### Sample source code for Sign With Smart Card Using Pdf File Signature using Aspose.PDF for .NET 
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

### FAQ's

#### Q: Why should I consider signing PDF files with a smart card?

A: Signing PDF files with a smart card enhances security by ensuring the authenticity and integrity of the document. Smart card-based signatures provide a higher level of trust and compliance.

#### Q: How does smart card-based digital signing work?

A: Smart card-based digital signing involves using a cryptographic key stored on a smart card to create a unique digital signature. This signature is attached to the PDF file, allowing recipients to verify the document's origin and integrity.

#### Q: What is the role of Aspose.PDF for .NET in smart card-based signing?

A: Aspose.PDF for .NET provides a comprehensive set of tools and libraries to facilitate smart card-based digital signing of PDF files. It simplifies the process and ensures secure document signing.

#### Q: Can I choose a specific smart card certificate for signing?

A: Yes, you can select a specific smart card certificate from the Windows certificate store for signing. Aspose.PDF for .NET allows you to seamlessly integrate certificate selection into your application.

#### Q: How does the provided source code handle smart card-based signing?

A: The source code demonstrates how to bind a PDF document, select a smart card certificate, specify signing information, and create a digital signature. It also shows how to verify the signature's validity.

#### Q: Can I apply multiple signatures using smart cards in a single PDF file?

A: Absolutely, you can apply multiple smart card-based signatures to a single PDF file. Each signature is unique and contributes to the document's overall security.

#### Q: What if a signature fails verification during the verification step?

A: If a signature fails verification, an exception is thrown, indicating that the signature is not valid. This ensures that only valid and trusted signatures are accepted.

#### Q: Is smart card-based signing compatible with all types of PDF documents?

A: Yes, smart card-based signing is compatible with all types of PDF documents. You can apply digital signatures to various types of PDF files, including forms, reports, and more.

#### Q: How can I learn more about advanced digital signature and certificate management?

A: Explore the official Aspose.PDF documentation for detailed insights into advanced digital signature features, certificate management, and best practices for ensuring document security.

#### Q: Where can I find further assistance or support for implementing smart card-based signing?

A: For additional guidance and support, reach out to the Aspose.PDF community forums or refer to the documentation for comprehensive information on smart card-based signing.