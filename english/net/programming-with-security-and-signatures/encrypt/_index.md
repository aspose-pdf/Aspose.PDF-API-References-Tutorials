---
title: Encrypt
linktitle: Encrypt
second_title: Aspose.PDF for .NET API Reference
description: Securely encrypt your PDF files with Aspose.PDF for .NET.
type: docs
weight: 60
url: /net/programming-with-security-and-signatures/encrypt/
---

Encrypting PDF files is an important security measure to protect confidential information. With Aspose.PDF for .NET you can easily encrypt your PDF files using the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here are the necessary import directives:

```csharp
using Aspose.Pdf;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file to be encrypted. Replace `"YOUR DOCUMENTS DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 3: Open the PDF document

Next, you need to open the PDF document you want to encrypt. Use the following code to load the document:

```csharp
Document document = new Document(dataDir + "Encrypt.pdf");
```

## Step 4: Encrypt PDF

Now you can encrypt the PDF using the following code:

```csharp
document. Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
```

In this example, we are using the RC4x128 encryption algorithm with the "user" and "owner" passwords. You can change these settings as needed.

## Step 5: Backup Encrypted PDF

Finally, you can save the encrypted PDF to the specified location using the following code:

```csharp
dataDir = dataDir + "Encrypt_out.pdf";
document. Save(dataDir);
```

Be sure to specify the desired path and filename for the encrypted PDF.

### Sample source code for Encrypt using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open document
Document document = new Document(dataDir+ "Encrypt.pdf");
// Encrypt PDF
document.Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
dataDir = dataDir + "Encrypt_out.pdf";
// Save updated PDF
document.Save(dataDir);
Console.WriteLine("\nPDF file encrypted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You now have a step-by-step overview of encrypting PDF files using Aspose.PDF for .NET. You can embed this code into your own projects to secure your PDF files with ease.

Be sure to check out the official Aspose.PDF documentation for more information on advanced encryption and security features.
