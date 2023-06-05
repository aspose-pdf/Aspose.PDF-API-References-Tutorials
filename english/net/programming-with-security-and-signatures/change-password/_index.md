---
title: Change Password
linktitle: Change Password
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /net/programming-with-security-and-signatures/change-password/
---
### Sample source code for Change Password using Aspose.Words for .NET 
```csharp
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_SecuritySignatures();
            // Open document
            Document document = new Document(dataDir+ "ChangePassword.pdf", "owner");
            // Change password
            document.ChangePasswords("owner", "newuser", "newowner");
            dataDir = dataDir + "ChangePassword_out.pdf";
            // Save updated PDF
            document.Save(dataDir);
            Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```