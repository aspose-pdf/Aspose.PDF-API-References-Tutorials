---
title: Flatten Forms In PDF Document
linktitle: Flatten Forms In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Easily flatten forms in PDF document using Aspose.PDF for .NET.
type: docs
weight: 100
url: /it/net/programming-with-forms/flatten-forms/
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

### FAQ's

#### Q: What does "flattening forms" mean in Aspose.PDF for .NET?

A: Flattening forms in Aspose.PDF for .NET refers to the process of making form fields in a PDF document uneditable and merging annotations (such as form fields, annotations, and digital signatures) with the document's content. Once forms are flattened, users cannot modify the form fields, and the visual appearance of the form fields becomes a part of the static content of the PDF document.

#### Q: Can I reverse the flattening process and make the form fields editable again?

A: No, once the form fields are flattened, the process is irreversible using Aspose.PDF for .NET. Flattening permanently merges the form fields' appearance with the PDF's content, and the individual form field elements are no longer accessible or editable.

#### Q: When should I flatten forms in a PDF document?

A: Flattening forms is useful when you want to preserve the visual appearance of form fields and annotations in a PDF document while preventing users from modifying the data. This is commonly done when you want to share a PDF document with pre-filled form data or annotations that should not be altered by the recipients.

#### Q: Will flattening forms affect other annotations, such as digital signatures?

A: Yes, flattening forms will merge all annotations, including digital signatures, with the PDF's content. Once the forms are flattened, any existing digital signatures will become a permanent part of the document, and users cannot modify or remove them.

#### Q: Can I selectively flatten specific form fields and leave others editable?

A: Yes, you can selectively flatten specific form fields in a PDF document while leaving others editable. Instead of using the code to flatten all form fields, you can choose to flatten only the desired form fields based on their names or other criteria.