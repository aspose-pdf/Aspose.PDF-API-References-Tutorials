---
title: Digitally Sign With Time Stamp
linktitle: Digitally Sign With Time Stamp
second_title: Aspose.PDF for .NET API Reference
description: Learn how to perform a digital signature with time stamp on a PDF file using Aspose.PDF for .NET.
type: docs
weight: 50
url: /net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

In this tutorial, we will walk you through the process of digitally signing a PDF file with time stamp using Aspose.PDF for .NET. The digital signature with timestamp guarantees the authenticity and integrity of the document, by adding an electronic fingerprint with a timestamp.

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
