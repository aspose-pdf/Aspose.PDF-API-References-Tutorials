---
title: Digitally Sign With Time Stamp In PDF File
linktitle: Digitally Sign With Time Stamp In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to digitally sign a PDF with a timestamp using Aspose.PDF for .NET. This step-by-step guide covers prerequisites, certificate setup, timestamping, and more.
type: docs
weight: 50
url: /net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Introduction

Have you ever needed to digitally sign a PDF and include a timestamp for extra security? Whether you’re working on legal documents, contracts, or anything that requires secure authentication, a digital signature with a timestamp adds an extra layer of credibility. In this tutorial, we’ll break down how you can use Aspose.PDF for .NET to add a digital signature along with a timestamp to your PDF documents. Don’t worry, we’ll take it step by step!

## Prerequisites

Before we dive into the code, there are a few things you’ll need to set up to follow along. Here’s a quick checklist of the prerequisites to get you started:

- Aspose.PDF for .NET Library: You’ll need the Aspose.PDF for .NET library installed in your project. You can [download the latest version here](https://releases.aspose.com/pdf/net/) or add it to your project via NuGet.
- A PDF document: You’ll need a sample PDF file to work with. Make sure to have a file in your project’s directory that you want to sign.
- Digital Certificate (PFX file): Ensure you have a digital certificate (a `.pfx` file) to digitally sign the document.
- Timestamping URL: This is an online timestamping service that will be used to attach a timestamp to the digital signature. 
- Basic C# knowledge: You don’t need to be an expert, but knowing the basics of C# will help you understand and customize the code.

Once you've ticked all these boxes, you're ready to start coding!

## Import Packages

To get started, you’ll need to import the following namespaces into your C# project. This ensures you have access to the relevant Aspose.PDF classes and functions.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Step 1: Load the PDF Document

The first thing we need to do is load the PDF document that we want to sign. Here’s how you do that:

```csharp
// Define the path to your document directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the PDF document
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

This step is pretty straightforward. We're simply defining the path to the document we want to sign. The `Document` class from Aspose.PDF handles loading the file.

## Step 2: Set Up the Digital Signature

Next, we’ll create the digital signature using the PKCS7 class and load the PFX file. This PFX file contains your certificate and private key, which are necessary for signing the document.

```csharp
// Path to your .pfx file
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Initialize the signature object
PdfFileSignature signature = new PdfFileSignature(document);

// Load the PFX file with a password
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

At this point, you're telling Aspose to use your digital certificate for signing the document. The `PKCS7` object handles all the cryptographic work for you, so you don't have to worry about the nitty-gritty details.

## Step 3: Add the Timestamp Settings

One of the key components of a robust digital signature is the timestamp. This ensures that the document’s signature can be verified even after the certificate has expired. Let’s set up the timestamp using an online timestamping authority.

```csharp
// Define timestamp settings
TimestampSettings timestampSettings = new TimestampSettings("https://your_timestamp_url", "user:password");

// Add timestamp settings to the PKCS7 object
pkcs.TimestampSettings = timestampSettings;
```

Here, you’re specifying the URL for the timestamping service, which will automatically provide a time and date to your signature. This can be done with or without authentication.

## Step 4: Define the Signature Location and Appearance

Now, we’ll define where the signature will appear in the PDF and its dimensions. You can customize the position of the signature box on the page, as well as the size.

```csharp
// Define the signature appearance and location (page 1, with specified rectangle)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Here, we’re defining a rectangle that positions the signature at coordinates (100, 100) on the first page of the PDF, with a width of 200 and height of 100. You can change these values to fit your design.

## Step 5: Sign the PDF Document

With everything set up, it’s time to actually apply the digital signature to the PDF. This step combines the certificate, timestamp, and positioning into one simple command.

```csharp
// Sign the document on the first page
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Here’s what’s happening:
- 1: This indicates that the signature should be applied to the first page.
- "Signature Reason": This is where you can specify why you’re signing the document.
- "Contact": Enter the contact information of the signer.
- "Location": Specify the location of the signer.
- true: This boolean value indicates whether the signature is visible in the document.
- rect: The rectangle we defined earlier specifies the size and position of the signature.
- pkcs: The PKCS7 object contains the digital certificate and timestamp settings.

## Step 6: Save the Signed PDF

Once the document is signed, all that’s left to do is save it. You can choose a new file name to keep both the original and the signed versions.

```csharp
// Save the signed PDF document
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Your newly signed and timestamped PDF is now saved to the specified directory!

## Conclusion

And there you have it! You’ve successfully digitally signed a PDF with a timestamp using Aspose.PDF for .NET. This process ensures the authenticity and integrity of your documents, giving both you and the recipient peace of mind. Digital signatures are becoming more and more essential in today’s digital world, so mastering this process is definitely a skill worth having.

## FAQ's

### Can I use a different file format for the certificate?  
Yes, but the tutorial focuses on using a PFX file, which is the most common format for digital certificates.

### Do I need an internet connection to apply the timestamp?  
Yes, since the timestamp is fetched from an online timestamping authority, you will need internet access.

### Can I sign multiple pages in a PDF?  
Absolutely! You can modify the `signature.Sign()` method to target multiple pages or loop through all the pages.

### What happens if the PFX file password is incorrect?  
You’ll receive an exception if the password is wrong, so make sure it’s entered correctly.

### Can I make the signature invisible?  
Yes, you can pass `false` to the `Sign` method's visibility parameter to make the signature invisible.
