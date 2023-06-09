---
title: Dynamic XFA To Acro Form
linktitle: Dynamic XFA To Acro Form
second_title: Aspose.PDF for .NET API Reference
description: Easily convert dynamic XFA To forms to standard AcroForm forms with Aspose.PDF for .NET.
type: docs
weight: 70
url: /content/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

In this tutorial, we will show you how to convert an XFA To dynamic form to an AcroForm using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the dynamic XFA form

Load the dynamic XFA form:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Step 3: Set Form Type as Standard AcroForm

Set the form type as standard AcroForm:

```csharp
document.Form.Type = FormType.Standard;
```

## Step 4: Save the Resulting PDF

Save the resulting PDF:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Sample source code for Dynamic XFA To Acro Form using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load dynamic XFA form
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Set the form fields type as standard AcroForm
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Save the resultant PDF
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we learned how to convert an XFA To dynamic form to a standard AcroForm form using Aspose.PDF for .NET. By following these steps, you can easily convert your dynamic XFATo forms to AcroForms for more common use.