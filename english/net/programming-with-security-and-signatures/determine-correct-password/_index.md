---
title: Determine Correct Password
linktitle: Determine Correct Password
second_title: Aspose.PDF for .NET API Reference
description: Learn how to determine the correct password for a PDF file with Aspose.PDF for .NET.
type: docs
weight: 30
url: /net/programming-with-security-and-signatures/determine-correct-password/
---

In this tutorial, we'll walk you through the process of determining the correct password for a PDF file using Aspose.PDF for .NET. This feature allows you to check if a PDF file is password protected and find the correct password from a predefined list.

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
```

## Step 3: Loading source PDF file

The first step is to upload the source PDF file you want to verify. In this example, we assume that you have a PDF file named "IsPasswordProtected.pdf" in the specified directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Be sure to replace the placeholders with the actual locations of your PDF file.

## Step 4: Determine Source PDF Encryption

Once you have uploaded the source PDF file, you can determine if it is encrypted using the `IsEncrypted` method of the `PdfFileInfo` object.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

This statement displays whether the PDF file is password protected or not.

## Step 5: Finding the correct password

Next, we will search for the correct password using a predefined list of passwords. We go through each password in the list and try to load the PDF document with that password.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

This loop tests each word of pass from the list. If the password is correct, the number of pages in the document is displayed. Otherwise, a message indicating that the password is not correct is displayed.


### Sample source code for Determine Correct Password using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Load source PDF file
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Determine if the source PDF is encrypted
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## 7. Conclusion

Congratulation ! You have successfully determined the correct password for a PDF file using Aspose.PDF for .NET. This tutorial covered the step-by-step process, from verifying file encryption to finding the correct password from a predefined list. Now you can use this feature to check and find the correct password of your PDF files.
