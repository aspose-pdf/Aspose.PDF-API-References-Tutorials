---
title: Set Privileges
linktitle: Set Privileges
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 100
url: /net/programming-with-security-and-signatures/set-privileges/
---
### Sample source code for Set Privileges using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
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