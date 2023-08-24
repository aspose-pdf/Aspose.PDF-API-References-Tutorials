---
title: Digitally Sign With Time Stamp In PDF File
linktitle: Digitally Sign With Time Stamp In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to perform a digital signature with time stamp in PDF file using Aspose.PDF for .NET.
type: docs
weight: 50
url: /tr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
In this tutorial, we will walk you through the process of digitally signing in PDF file with time stamp using Aspose.PDF for .NET. The digital signature with timestamp guarantees the authenticity and integrity of the document, by adding an electronic fingerprint with a timestamp.

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
```

## Step 3: Digital signature with timestamp

The first step is to perform the digital signature with timestamp on the PDF file. The provided code shows how to achieve this signature with Aspose.PDF for .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

This code loads a PDF file, creates a digital signature with timestamp using a PFX file (private key) and the specified timestamp parameters. The signature is then added to the PDF file and saved with the suffix "_out".

### Sample source code for Digitally Sign With Time Stamp using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // User/Password can be omitted
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Create any of the three signature types
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Save output PDF file
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusion

Congratulation ! You have successfully performed a digital signature with timestamp on a PDF file using Aspose.PDF for .NET. This tutorial covered the step-by-step process from creating the signature to saving the updated PDF file. You can now use this feature to add digital signatures with timestamp to your PDF files.

### FAQ's for digitally sign with time stamp in PDF file

#### Q: What is the purpose of digitally signing with a timestamp?

A: Digitally signing with a timestamp adds an electronic fingerprint with a timestamp to a PDF file, ensuring the document's authenticity and integrity at a specific point in time.

#### Q: What prerequisites are needed to start this tutorial?

A: Before you begin, ensure you have a basic understanding of the C# programming language, have Visual Studio installed, and have the Aspose.PDF library for .NET installed.

#### Q: How can I set up my development environment?

A: Follow the provided steps to set up your development environment, including creating a new C# project in Visual Studio and importing the necessary namespaces.

#### Q: How do I add a digital signature with a timestamp to a PDF?

A: The provided sample code demonstrates how to load a PDF file, create a digital signature with a timestamp using a PFX file (private key) and specified timestamp settings, add the signature to the PDF file, and save the updated file.

#### Q: What is a PFX file, and why is it used in the example?

A: A PFX (Personal Exchange Format) file contains a private key and certificate. It's used here to provide cryptographic functionality for digital signatures. Ensure you replace the placeholder with your PFX file and password.

#### Q: What are TimestampSettings?

A: TimestampSettings define the settings for the timestamp server used to add the electronic timestamp to the signature. It includes the timestamp server URL and optional user credentials.

#### Q: Can I use a timestamp server other than the one in the example?
A: Yes, you can use any compatible timestamp server. Replace the URL and, if required, provide the appropriate user credentials in the `TimestampSettings` object.

#### Q: What is the purpose of specifying the signature rectangle?

A: The signature rectangle defines the position and dimensions of the digital signature appearance on the PDF page. Adjust these values to position the signature as desired.

#### Q: What happens if the timestamp server is unavailable during signing?

A: If the timestamp server is unavailable during signing, the process may fail or take longer. Ensure your timestamp server is reliable and accessible.

#### Q: How can I verify the presence of a timestamp in the signed PDF?

A: You can examine the signed PDF using the sample code provided. The `TimestampSettings` you used during signing should be available in the signature details.

#### Q: Are digital signatures with timestamps legally binding?

A: Digital signatures with timestamps hold legal value in many jurisdictions and are often considered more reliable than simple digital signatures. Consult legal experts in your jurisdiction for specific regulations.

#### Q: Can I add multiple digital signatures with timestamps to a PDF?

A: Yes, you can add multiple digital signatures with timestamps to a PDF file by calling the signature creation process multiple times. Each signature will have its own timestamp.