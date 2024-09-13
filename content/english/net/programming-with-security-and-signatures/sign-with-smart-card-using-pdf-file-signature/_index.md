---
title: Sign With Smart Card Using PDF File Signature
linktitle: Sign With Smart Card Using PDF File Signature
second_title: Aspose.PDF for .NET API Reference
description: Learn how to sign PDF files using a smart card with Aspose.PDF for .NET. Follow this step-by-step guide for secure digital signatures.
type: docs
weight: 110
url: /net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Introduction

In the digital age, securing documents is more crucial than ever. Whether it's a contract, an agreement, or any sensitive information, ensuring that the document is authentic and hasn't been tampered with is paramount. Enter digital signatures! Today, we’ll delve into how to sign a PDF file using a smart card with Aspose.PDF for .NET. This powerful library allows developers to manipulate and create PDF documents efficiently, including adding secure digital signatures. So, grab your smart card, and let's get started!

## Prerequisites

Before we jump into the nitty-gritty of signing a PDF file, let’s make sure you have everything you need. Here’s a checklist to help you prepare:

1. Aspose.PDF for .NET: Ensure you have the Aspose.PDF library installed. You can download it from the [site](https://releases.aspose.com/pdf/net/).
2. Visual Studio: A development environment where you can write and run your .NET code.
3. Smart Card: You’ll need a smart card with a valid digital certificate installed.
4. Basic Understanding of C#: Familiarity with C# programming will be beneficial as we’ll be writing code snippets in this language.
5. PDF Document: A sample PDF file (like `blank.pdf`) to test our signing process.

With these prerequisites in place, you’re ready to dive into the code!

## Import Packages

First things first, let’s import the necessary packages. You’ll need to add references to the Aspose.PDF library in your project. Here’s how you can do it:

1. Open Visual Studio.
2. Create a new project or open an existing one.
3. Right-click on your project in the Solution Explorer and select `Manage NuGet Packages`.
4. Search for `Aspose.PDF` and install the latest version.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Now that we have the necessary packages imported, let’s break down the code step by step.

## Step 1: Set Up Your Document

The first step in our process is to set up the PDF document we want to sign. Here’s how you can do that:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
In this snippet, we define the path to our documents directory and create an instance of the `Document` class using a sample PDF file named `blank.pdf`. Make sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path where your PDF is located.

## Step 2: Initialize PdfFileSignature

Next, we’ll initialize the `PdfFileSignature` class, which is responsible for handling the signing process.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Here, we create an instance of `PdfFileSignature` and bind it to our PDF document. This prepares the document for signing.

## Step 3: Access the Smart Card Certificate

Now comes the crucial part—accessing the digital certificate stored on your smart card. This is how we can do it:

### Open the Certificate Store

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
We open the certificate store located in the current user’s profile. This allows us to access the certificates installed on your machine, including those on your smart card.

### Select the Certificate

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
This code prompts the user to select a certificate from the collection. The user interface will display all available certificates, allowing you to choose the one associated with your smart card.

## Step 4: Create the External Signature

Once you have selected your certificate, the next step is to create an external signature using the selected certificate.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Here, we create an instance of `ExternalSignature` using the selected certificate. This object will be used to sign the PDF document.

## Step 5: Set Signature Appearance

Now, let’s set the appearance of our signature. This is where you can customize how your signature looks on the document.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
In this snippet, we specify the appearance of the signature by providing the path to an image file (like a logo or a signature graphic). Make sure to replace `"demo.png"` with the actual image you want to use.

## Step 6: Sign the PDF

With everything set up, it’s time to sign the PDF document!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
In this step, we call the `Sign` method on our `pdfSign` object. Here’s what each parameter means:
- `1`: The page number where the signature will appear.
- `"Reason"`: The reason for signing the document.
- `"Contact"`: Contact information for the signer.
- `"Location"`: The location of the signer.
- `true`: Indicates whether to create a visible signature.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: The position and size of the signature on the PDF.
- `externalSignature`: The signature object we created earlier.

Finally, we save the signed document as `externalSignature2.pdf`.

## Step 7: Verify the Signature

After signing the document, it’s essential to verify that the signature is valid. Here’s how to do that:

### Initialize Verification Process

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
We create a new instance of `PdfFileSignature` for the signed document. We then retrieve the names of all signatures present in the document.

### Check Signature Validity

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
We loop through each signature name and verify its validity. If any signature fails verification, an exception is thrown, indicating that the signature is not valid.

## Conclusion

And there you have it! You’ve successfully signed a PDF document using a smart card with Aspose.PDF for .NET. This process not only secures your document but also adds a layer of authenticity that is crucial in today’s digital world. Whether you're dealing with contracts, legal documents, or any sensitive information, knowing how to implement digital signatures is a valuable skill. 

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a powerful library that allows developers to create, manipulate, and convert PDF documents within .NET applications.

### Do I need a smart card for signing PDFs?
While a smart card is not mandatory, it is highly recommended for secure digital signatures, as it provides an added layer of security.

### Can I use any PDF file to sign?
Yes, you can use any PDF file, but ensure it’s not password-protected. If it is, you’ll need to unlock it first.

### What if I don’t have a digital certificate?
You can obtain a digital certificate from a trusted certificate authority (CA) or use a self-signed certificate for testing purposes.

### Is there a trial version of Aspose.PDF available?
Yes, you can download a free trial version from the [Aspose website](https://releases.aspose.com/).
