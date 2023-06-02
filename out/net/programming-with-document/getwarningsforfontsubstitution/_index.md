---
title: Get Warnings For Font Substitution
linktitle: Get Warnings For Font Substitution
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use the GetWarningsForFontSubstitution feature of Aspose.PDF for .NET to detect font substitution warnings when opening a PDF document.
type: docs
weight: 190
url: /content/net/programming-with-document/getwarningsforfontsubstitution/
---

Aspose.PDF for .NET is a popular PDF manipulation library that enables developers to create, edit, and convert PDF files in their .NET applications. One of the features offered by this library is the ability to detect font substitution warnings when a PDF document is opened. This tutorial will guide you through the steps of using the `GetWarningsForFontSubstitution` feature of Aspose.PDF for .NET to detect font substitution warnings when opening a PDF document.

## Step 1: Install Aspose.PDF for .NET

To use Aspose.PDF for .NET in your .NET applications, you must first install the library. You can download the latest version of the library from the [Aspose.PDF for .NET download page](https://relases.aspose.com/pdf/net).

Once you have downloaded the library, extract the contents of the ZIP file to a folder on your computer. You will then need to add a reference to the Aspose.PDF for .NET DLL in your .NET project.

## Step 2: Load the PDF Document

Once you have installed Aspose.PDF for .NET and added a reference to the DLL in your .NET project, you can begin using the `GetWarningsForFontSubstitution` feature to detect font substitution warnings when opening a PDF document.

The first step in using this feature is to load the PDF document that you want to detect font substitution warnings for. To do this, you can use the following code:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document doc = new Document(dataDir + "input.pdf");
```

In the above code, replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your PDF document is located. This code will load the PDF document into a `Document` object, which you can then use to detect font substitution warnings.

## Step 3: Detect Font Substitution Warnings

To detect font substitution warnings when opening a PDF document, you can use the following code:

```csharp
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);
```

In the above code, `OnFontSubstitution` is a method that will be called whenever a font substitution warning is detected. You can customize this method to handle the font substitution warning in any way that you like.

Here is an example implementation of the `OnFontSubstitution` method:

```csharp
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```

In the above code, the `OnFontSubstitution` method simply outputs the original font name and the substituted font name to the console whenever a font substitution warning is detected. You can customize this method to handle the font substitution warning in any way that you like.

### Example source code for Get Warnings For Font Substitution using Aspose.NET for PDF

Here is the full source code for detecting font substitution warnings when opening a PDF document using the `GetWarningsForFontSubstitution` feature of Aspose.PDF for .NET:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document doc = new Document(dataDir + "input.pdf");

// Detect font substitution warnings
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);

// Handle font substitution warning
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```