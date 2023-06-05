---
title: Set Privileges
linktitle: Set Privileges
second_title: Aspose.PDF for .NET API Reference
description: Easily set access privileges for your PDF files with Aspose.PDF for .NET.
type: docs
weight: 100
url: /net/programming-with-security-and-signatures/set-privileges/
---

It is often necessary to set specific access privileges for PDF files. With Aspose.PDF for .NET, you can easily set access privileges using the following source code:

## Step 1: Import required libraries

Before you begin, you need to import the necessary libraries for your C# project. Here are the necessary import directives:

```csharp
using Aspose.Pdf;
```

## Step 2: Set path to documents folder

In this step, you need to specify the path to the folder containing the PDF file you want to edit. Replace `"YOUR DOCUMENTS DIRECTORY"` in the following code with the actual path to your documents folder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 3: Load source PDF file

Now we will load the source PDF file using the following code:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Step 4: Set Access Privileges

In this step, we will instantiate the `DocumentPrivilege` object to set the desired access privileges. You can apply restrictions on all privileges using `DocumentPrivilege.ForbidAll`. For example, if you want to only allow screen reading, you can set `AllowScreenReaders` to `true`. Here is the corresponding code:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Step 5: Encrypt and save the document

Finally, we can encrypt the PDF document with a user and owner password using `Encrypt` and specifying the desired encryption algorithm. Then we save the updated document. Here is the corresponding code:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Sample source code for Set Privileges using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Load a source PDF file
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Instantiate Document Privileges object
	// Apply restrictions on all privileges
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Only allow screen reading
	documentPrivilege.AllowScreenReaders = true;
	// Encrypt the file with User and Owner password.
	// Need to set the password, so that once the user views the file with user password,
	// Only screen reading option is enabled
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Save updated document
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Conclusion

Congratulation ! You now have a step-by-step guide to set access privileges for a PDF document using Aspose.PDF for .NET. You can use this code to apply specific restrictions and protect your PDF files as needed.

Be sure to check out the official Aspose.PDF documentation for more information on advanced PDF document security and access privilege management features.
