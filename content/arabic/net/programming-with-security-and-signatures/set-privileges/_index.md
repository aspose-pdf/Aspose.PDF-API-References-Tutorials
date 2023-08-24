---
title: Set Privileges In PDF File
linktitle: Set Privileges In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily set access privileges in PDF file with Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-security-and-signatures/set-privileges/
---
It is often necessary to set specific access privileges in PDF file. With Aspose.PDF for .NET, you can easily set access privileges using the following source code:

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

### Sample source code for Set Privileges using Aspose.PDF for .NET 
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

### FAQ's for set privileges in PDF file

#### Q: Why would I need to set access privileges in a PDF file?

A: Setting access privileges allows you to control how users interact with your PDF documents. You can restrict actions like printing, copying, and editing to enhance document security.

#### Q: How can I benefit from setting access privileges using Aspose.PDF for .NET?

A: Aspose.PDF for .NET provides a straightforward way to implement access privileges, giving you the power to customize user permissions and protect sensitive content.

#### Q: Can I apply different privileges for different users?

A: Yes, you can set specific access privileges for different user groups, enabling you to fine-tune document access based on user roles.

#### Q: What are some common access privileges I can set?

A: Common access privileges include allowing or forbidding actions such as printing, copying text or images, modifying the document, and filling form fields.

#### Q: How does setting screen reading privilege enhance document accessibility?

A: Enabling screen reading privilege ensures that users can access the content of the PDF using screen readers, enhancing accessibility for visually impaired individuals.

#### Q: Can I set password protection along with access privileges?

A: Absolutely, you can encrypt your PDF document with passwords while applying access privileges. This provides an extra layer of security.

#### Q: Is there a way to revoke access privileges after applying them?

A: Once access privileges are applied and the document is encrypted, users will need the appropriate password to access the content. The privileges can be modified by altering the source code.

#### Q: Are there any performance considerations when setting access privileges?

A: The performance impact is minimal, as the access privilege settings are applied during encryption, which is a swift process.

#### Q: Can I apply access privileges to an existing PDF document?

A: Yes, you can use Aspose.PDF for .NET to apply access privileges to both new and existing PDF documents.