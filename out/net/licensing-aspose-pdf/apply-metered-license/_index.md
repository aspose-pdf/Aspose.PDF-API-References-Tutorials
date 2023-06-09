---
title: Configure Metered License
linktitle: Configure Metered License
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to set up a metered license with Aspose.PDF for .NET and benefit from advanced features.
type: docs
weight: 10
url: /content/net/licensing-aspose-pdf/configure-metered-license/
---

In this tutorial, we will walk you through step-by-step how to set up a metered license with Aspose.PDF for .NET. The metered license allows you to use the advanced features of Aspose.PDF based on your actual consumption.

### Step 1: Configuring License Keys

In the source code provided, you must specify the public and private keys of the metered license. Replace the "*****" values with your own keys. These keys will be provided to you when you purchase a metered license from Aspose.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### Step 2: Loading the document

Load the PDF document from disk using the `Document` class of Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### Step 3: Get Document Page Count

Use the `Count` property of the `Pages` collection to get the total number of pages in the document.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Sample source code for Configure Metered License using Aspose.PDF for .NET 

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

## Conclusion

In this tutorial, we explained how to set up a metered license with Aspose.PDF for .NET. By using a metered license, you can benefit from the advanced features of Aspose.PDF based on your actual usage. Make sure to provide valid license keys to use Aspose.PDF with all its features.
