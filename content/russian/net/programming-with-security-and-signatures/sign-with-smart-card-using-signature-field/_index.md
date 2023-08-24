---
title: Sign With Smart Card Using Signature Field
linktitle: Sign With Smart Card Using Signature Field
second_title: Aspose.PDF for .NET API Reference
description: Sign your PDF files securely with a smart card using Aspose.PDF for .NET.
type: docs
weight: 120
url: /ru/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Digital signing with a smart card is a secure way to sign PDF files. With Aspose.PDF for .NET, you can easily sign a PDF file using a signature field and a smart card by following the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here are the necessary import directives:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to sign. Replace `"YOUR DOCUMENTS DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 3: Copy and open the PDF document

Now we will copy and open the PDF document to be signed using the following code:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Create a signature field
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Select the certificate in the store
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Create an external signature with the necessary information
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
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
```

## Step 4: Verify Signature

Finally, we verify the signature of the signed PDF file using the `PdfFileSignature` class. We get the signature names and check them one by one. If a signature fails verification, an exception is thrown. Here is the corresponding code:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Sample source code for Sign With Smart Card Using Signature Field using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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

## Conclusion

Congratulation ! You now have a step-by-step guide to signing a PDF file with a smart card using a signature field with Aspose.PDF for .NET. You can use this code to add secure digital signatures to your PDF documents.

Be sure to check out the official Aspose.PDF documentation for more information on advanced digital signature and certificate management features.

### FAQ's

#### Q: What is the benefit of using a signature field for digital signing with a smart card?

A: Using a signature field for digital signing with a smart card provides a designated area within the PDF where the signature is applied. This enhances document clarity and ensures the signature's authenticity.

#### Q: How does the Aspose.PDF for .NET library facilitate smart card-based digital signing with a signature field?

A: Aspose.PDF for .NET simplifies the process of creating a signature field, selecting a smart card certificate, and applying a digital signature to a specific area within the PDF document.

#### Q: Why is selecting a specific certificate important for smart card-based signing?

A: Selecting a specific certificate allows you to uniquely identify the signer and ensure the integrity of the signature. This helps establish trust and compliance with digital signing standards.

#### Q: How does the provided source code handle the smart card-based signing process with a signature field?

A: The source code demonstrates how to create a signature field, select a smart card certificate, and apply a digital signature with specific signing information. It also shows how to verify the signature's validity.

#### Q: Can I customize the appearance of the signature field?

A: Yes, you can customize the appearance of the signature field, such as its size, position, and visual representation, to align with your document's layout.

#### Q: What happens if a signature fails verification during the verification step?

A: If a signature fails verification, an exception is thrown, indicating that the signature is not valid. This ensures that only valid and trusted signatures are accepted.

#### Q: Can I apply multiple signature fields and smart card-based signatures to a single PDF document?

A: Absolutely, you can apply multiple signature fields and smart card-based signatures to different areas of the same PDF document, providing multiple layers of security.

#### Q: How does using a signature field enhance the overall document signing process?

A: Using a signature field streamlines the document signing process, as it guides the signer to place their signature in a designated area, making the signing process more organized and user-friendly.

#### Q: Are there any limitations to using signature fields with smart card-based signing?

A: There are no inherent limitations to using signature fields with smart card-based signing. However, it's important to ensure that the chosen signature field location doesn't obscure important document content.

#### Q: Where can I find further assistance or support for implementing smart card-based signing with a signature field?

A: For additional guidance and support, you can refer to the official Aspose.PDF documentation and community forums, which offer valuable insights and solutions for implementing secure digital signatures.