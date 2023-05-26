---
title: Get All Fonts
linktitle: Get All Fonts
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to get all the fonts used in a PDF document programmatically with this step-by-step guide and example code.
type: docs
weight: 160
url: /net/programming-with-document/getallfonts/
---

Aspose.PDF for .NET is a powerful library that enables developers to work with PDF documents programmatically. One of the features that it provides is the ability to get all the fonts used in a PDF document. This can be useful if you need to programmatically analyze or manipulate the fonts in a PDF document.

In this tutorial, we will discuss how to use Aspose.PDF for .NET to get all the fonts used in a PDF document. We will provide a step-by-step guide on how to do this, along with example source code.

## Step 1: Create a new C# Console Application
To get started, create a new C# Console Application in Visual Studio. You can name it whatever you like. Once the project is created, you need to add a reference to the Aspose.PDF for .NET library.

## Step 2: Import the Aspose.PDF Namespace
Add the following line of code at the top of your C# file to import the Aspose.PDF namespace:

```csharp
using Aspose.Pdf;
```

## Step 3: Load the PDF Document
Load the PDF document that you want to get the fonts from:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Step 4: Get All the Fonts
Get all the fonts used in the PDF document:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Step 5: Print All the Fonts
Print all the fonts used in the PDF document:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Example source code for Get All Fonts using Aspose.PDF for .NET
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Conclusion
In this tutorial, we have discussed how to get all the fonts used in a PDF document using Aspose.PDF for .NET. Getting all the fonts used in a PDF document can be useful if you need to programmatically analyze or manipulate the fonts in a PDF document. Aspose.PDF for .NET provides a simple and easy-to-use API to work with PDF documents, including getting all the fonts used in a PDF document.



