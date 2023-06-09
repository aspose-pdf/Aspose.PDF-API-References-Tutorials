---
title: Flatten Forms
linktitle: Flatten Forms
second_title: Aspose.PDF for .NET API Reference
description: Easily flatten forms in your PDF documents using Aspose.PDF for .NET.
type: docs
weight: 100
url: /content/net/programming-with-forms/flatten-forms/
---

In this tutorial, we will show you how to flatten forms using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load source PDF form

Load the source PDF form:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Step 3: Flatten the forms

First check if there are any form fields in the document. If so, iterate through each field and apply flattening:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Step 4: Save the updated document

Save the updated PDF document:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Flatten Forms using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load source PDF form
Document doc = new Document(dataDir + "input.pdf");
// Flatten Forms
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Save the updated document
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to flatten forms using Aspose.PDF for .NET. By following these steps, you can easily flatten forms in your PDF documents, making fields uneditable and merging annotations with document content.