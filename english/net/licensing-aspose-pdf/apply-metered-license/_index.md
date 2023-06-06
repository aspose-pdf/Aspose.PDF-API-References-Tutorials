---
title: Setting Metered License
linktitle: Setting Metered License
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 10
url: /net/licensing-aspose-pdf/apply-metered-license/
---
### Sample source code for Apply Metered License using Aspose.Words for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// set metered public and private keys
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.SetMeteredKey("*****", "*****");
// Load the document from disk.
Document doc = new Document(dataDir + "input.pdf");
//Get the page count of document
Console.WriteLine(doc.Pages.Count);

```