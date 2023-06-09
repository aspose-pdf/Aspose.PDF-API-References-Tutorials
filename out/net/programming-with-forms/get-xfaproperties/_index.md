---
title: Get XFAProperties
linktitle: Get XFAProperties
second_title: Aspose.PDF for .NET API Reference
description: Easily get XFA properties of form fields in your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 160
url: /content/net/programming-with-forms/get-xfaproperties/
---

In this tutorial, we will show you how to get XFA properties of form fields in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the XFA form

Load the XFA form from the PDF document:

```csharp
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
```

## Step 3: Get field names

Get XFA field names:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Step 4: Set Field Values

Set values for XFA fields:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Step 5: Get fields position

Get the position of XFA fields:

```csharp
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
```

## Step 6: Save the updated document

Save the updated PDF document:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Get XFAProperties using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load XFA form
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
string[] names = doc.Form.XFA.FieldNames;
// Set field values
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
// Get field position
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
// Get field position
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
dataDir = dataDir + "Filled_XFA_out.pdf";
// Save the updated document
doc.Save(dataDir);
Console.WriteLine("\nXFA fields properties retrieved successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to get XFA properties of form fields in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily extract XFA field information, such as positions, from PDF documents using Aspose.PDF.