---
title: Fill XFAFields
linktitle: Fill XFAFields
second_title: Aspose.PDF for .NET API Reference
description: Easily fill XFA fields in your PDF documents using Aspose.PDF for .NET.
type: docs
weight: 90
url: /content/net/programming-with-forms/fill-xfafields/
---

In this tutorial, we will show you how to fill XFA fields using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the XFA form

Load the XFA form:

```csharp
Document doc = new Document(dataDir + "FillXFAFields.pdf");
```

## Step 3: Get XFA Field Names

Get the form's XFA field names:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Step 4: Set Field Values

Set the XFA field values using the names obtained earlier:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Step 5: Save the updated document

Save the updated PDF document:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Fill XFAFields using Aspose.Words for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load XFA form
Document doc = new Document(dataDir + "FillXFAFields.pdf");
// Get names of XFA form fields
string[] names = doc.Form.XFA.FieldNames;
// Set field values
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
dataDir = dataDir + "Filled_XFA_out.pdf";
// Save the updated document
doc.Save(dataDir);
Console.WriteLine("\nXFA fields filled successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to fill XFA fields using Aspose.PDF for .NET. By following these steps, you can easily change the values of XFA fields in your PDF documents using Aspose.PDF.