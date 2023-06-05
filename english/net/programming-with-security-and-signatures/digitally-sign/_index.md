---
title: Digitally Sign
linktitle: Digitally Sign
second_title: Aspose.PDF for .NET API Reference
description: Learn how to digitally sign a PDF file with Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/programming-with-security-and-signatures/digitally-sign/
---

In this tutorial, we will walk you through the process of digitally signing a PDF file using Aspose.PDF for .NET. The digital signature guarantees the authenticity and integrity of the document, by adding a unique electronic fingerprint.

## Step 1: Prerequisites

Before you begin, make sure you have the following prerequisites:

- Basic knowledge of the C# programming language
- Installing Visual Studio on your machine
- Aspose.PDF library for .NET installed

## Step 2: Environment setup

To get started, follow these steps to set up your development environment:

1. Open Visual Studio and create a new C# project.
2. Import the required namespaces into your code file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Step 3: Digital signature

The first step is to digitally sign the PDF file. The provided code shows how to make a digital signature with Aspose.PDF for .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

This code loads a PDF file, creates a digital signature with a specified appearance, then saves the PDF file with the added signature.

## Step 4: Signature Verification

After adding the digital signature, you can check if the PDF file contains a valid signature.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Do something
                     }
                 }
             }
         }
     }
}
```

This code verifies the first signature of the PDF file and performs additional actions if the signature is certified and has specific permissions.

### Sample source code for Digitally Sign using Aspose.Words for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
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

## Conclusion

Congratulation ! You have successfully performed a digital signature on a PDF file using Aspose.PDF for .NET. This tutorial covered the step-by-step process, from adding the digital signature to verifying its validity. You can now use this feature to secure your PDF files with digital signatures.
