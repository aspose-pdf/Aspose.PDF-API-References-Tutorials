---
title: Replace Missing Fonts
linktitle: Replace Missing Fonts
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to replace missing fonts in a PDF file using Aspose.PDF for .NET.
type: docs
weight: 260
url: /net/document-conversion/replace-missing-fonts/
---
In this tutorial, we will walk you through the process of replacing missing fonts in a PDF file using Aspose.PDF for .NET. When you open a PDF file on a machine where a specific font is missing, there may be font display issues. In such cases, it is possible to substitute the missing font with another font available on the machine. By following the steps below, you will be able to replace missing fonts in a PDF file.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Finding the missing font
The first step is to find the missing font in the PDF file. Use the following code:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Find the original font
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // The font is missing on the destination machine
     // Add simple font substitution
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Replace missing font
Next, we'll replace the missing font with another available font. Use the following code:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Convert the PDF file to PDF/A format with error removal
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Save the resulting PDF file
pdf.Save(fileNew.FullName);
```

Be sure to replace `"input.pdf"` with the actual path to your original PDF file and `"newfile_out.pdf"` with the desired name for the resulting PDF file.

## Step 3: Saving the resulting PDF file
Finally, we'll save the resulting PDF file with the replaced font. Use the following code:

```csharp
// Save the resulting PDF file
pdf.Save(fileNew.FullName);
```

Ensures make sure you have set the correct destination path for the resulting PDF file.

### Example source code for Replace Missing Fonts using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Font is missing on destination machine
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Conclusion
In this tutorial, we covered the step-by-step process of replacing missing fonts in a PDF file using Aspose.PDF for .NET. By following the instructions outlined above, you will be able to successfully replace missing fonts in your PDF file.

### FAQ's

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that enables developers to work with PDF documents in C# applications. It offers various functionalities, including the ability to replace missing fonts in PDF files.

#### Q: Why would I encounter missing fonts in a PDF file?

A: Missing fonts in a PDF file can occur when the file is opened on a machine that does not have the necessary fonts installed. This can lead to font substitution, affecting the visual appearance of the document.

#### Q: How can I find and replace missing fonts in a PDF file using Aspose.PDF for .NET?

A: To find and replace missing fonts, you can use the `FontRepository.FindFont` method to check for the presence of the required font. If the font is missing, you can add a font substitution using the `FontRepository.Substitutions` property.

#### Q: Can I customize the font substitution process?

A: Yes, you can customize the font substitution process by specifying a different font for the substitution. In the code provided, we used Arial as the substitute for the missing "AgencyFB" font, but you can choose a different font according to your preferences.

#### Q: How can I ensure the accuracy of font rendering after substitution?

A: Aspose.PDF for .NET provides robust font handling capabilities, ensuring accurate font rendering after substitution. You can preview the resulting PDF file to verify the font replacement.
