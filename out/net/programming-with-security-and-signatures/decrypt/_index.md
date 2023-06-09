---
title: Decrypt
linktitle: Decrypt
second_title: Aspose.PDF for .NET API Reference
description: Learn how to decrypt PDF files using Aspose.PDF for .NET.
type: docs
weight: 20
url: /content/net/programming-with-security-and-signatures/decrypt/
---

In this tutorial, we will guide you through the process of decrypting a PDF file using Aspose.PDF for .NET. This library allows you to open an existing PDF file, decrypt it and save the updated version. This feature is useful when you need to remove the password from a PDF file for easier access.

## Step 1: Prerequisites

Before you begin, make sure you have the following prerequisites:

- Basic knowledge of the C# programming language
- Installing Visual Studio on your machine
- Aspose.PDF library for .NET installed

## Step 2: Environment setup

To get started, follow these steps to set up your development environment:

1. Open Visual Studio and create a new C# project.
2. Install Aspose.PDF library for .NET using NuGet package manager.
3. Import the required namespaces into your code file:

```csharp
using Aspose.Pdf;
```

## Step 3: Opening the PDF document

The first step is to open the PDF document you want to decrypt. In this example, we assume that you have a PDF file named "Decrypt.pdf" in the specified directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "Decrypt.pdf", "password");
```

Be sure to replace the placeholders with the actual locations and passwords you want to use.

## Step 4: PDF decryption

Once you have opened the PDF document, you can decrypt it using the `Decrypt` method. No parameters are required for this method.

```csharp
document. Decrypt();
```

## Step 5: Save updated PDF

After decrypting the PDF, you need to save the updated version of the document. Specify the output file path and use the `Save` method to save the document.

```csharp
dataDir = dataDir + "Decrypt_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file decrypted successfully.\nFile saved at " + dataDir);
```

The updated PDF will be saved to the specified location.

### Sample source code for Decrypt using Aspose.PDF for .NET 

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open document
Document document = new Document(dataDir+ "Decrypt.pdf", "password");
// Decrypt PDF
document.Decrypt();
dataDir = dataDir + "Decrypt_out.pdf";
// Save updated PDF
document.Save(dataDir);
Console.WriteLine("\nPDF file decrypted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You have successfully decrypted a PDF file using Aspose.PDF for .NET. This tutorial covered the step-by-step process from opening the document to saving the updated version. You can now use this feature to remove passwords from your PDF files.