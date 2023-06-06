---
title: Change Password
linktitle: Change Password
second_title: Aspose.PDF for .NET API Reference
description: Learn how to change the password of a PDF document using Aspose.PDF for .NET.
type: docs
weight: 10
url: /net/programming-with-security-and-signatures/change-password/
---

In this tutorial, we will guide you through the process of changing the password of a PDF document using Aspose.PDF for .NET. The library allows you to open an existing PDF file, modify its password, and save the updated version. This feature comes in handy when you need to secure your PDF documents by changing the password.

## Step 1: Requirements

Before we begin, make sure you have the following prerequisites:

- Basic knowledge of C# programming language
- Visual Studio installed on your machine
- Aspose.PDF for .NET library installed

## Step 2: Setting up the Environment

To get started, follow these steps to set up your development environment:

1. Open Visual Studio and create a new C# project.
2. Install the Aspose.PDF for .NET library using NuGet Package Manager.
3. Import the required namespaces into your code file:

```csharp
using Aspose.Pdf;
```

## Step 3: Loading the PDF Document

The first step is to load the PDF document that you want to change the password for. In this example, we assume that you have a PDF file named "ChangePassword.pdf" in the specified directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "ChangePassword.pdf", "owner");
```

## Step 4: Changing the Password

Once you have loaded the PDF document, you can change its password using the `ChangePasswords` method. The method requires three parameters: the current owner password, the new user password, and the new owner password.

```csharp
document.ChangePasswords("owner", "newuser", "newowner");
```

Make sure to replace the placeholders with the actual passwords you want to set.

## Step 5: Saving the Updated PDF

After changing the password, you need to save the updated PDF document. Specify the output file path and use the `Save` method to save the document.

```csharp
dataDir = dataDir + "ChangePassword_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

The updated PDF will be saved at the specified location.

### Sample source code for Change Password using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open document
Document document = new Document(dataDir+ "ChangePassword.pdf", "owner");
// Change password
document.ChangePasswords("owner", "newuser", "newowner");
dataDir = dataDir + "ChangePassword_out.pdf";
// Save updated PDF
document.Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulations! You have successfully changed the password of a PDF document using Aspose.PDF for .NET. This tutorial covered the step-by-step process, from loading the document to saving the updated version. You can now use this feature to secure your PDF files with new passwords.