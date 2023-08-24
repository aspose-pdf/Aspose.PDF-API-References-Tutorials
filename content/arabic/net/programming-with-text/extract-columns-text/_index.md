---
title: Extract Columns Text In PDF File
linktitle: Extract Columns Text In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract columns text in PDF file using Aspose.PDF for .NET.
type: docs
weight: 150
url: /ar/net/programming-with-text/extract-columns-text/
---
This tutorial will guide you through the process of extracting columns text in PDF file using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to extract columns text, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Open the PDF document
Open an existing PDF document using the `Document` constructor and passing the path to the input PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Step 5: Adjust the font size
Reduce the font size of the text fragments by a factor of 0.7 to enhance readability and better represent columnar text.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Step 6: Extract text from columns
Save the modified PDF document to a memory stream and reload it as a new document. Then, use the `TextAbsorber` class to extract text from the columns.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Step 7: Save the extracted text
Save the extracted text to a text file at the specified output file path.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Sample source code for Extract Columns Text using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Need to reduce font size at least for 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusion
You have successfully extracted columns text from a PDF document using Aspose.PDF for .NET. The extracted text has been saved to the specified output file.

### FAQ's

#### Q: What is the purpose of this tutorial?

A: This tutorial offers a step-by-step guide on extracting columns of text from a PDF file using Aspose.PDF for .NET. The accompanying C# source code provides a practical demonstration of the required procedures.

#### Q: What namespaces should I import?

A: In the code file where you intend to extract columns of text, include the following using directives at the beginning of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Q: How do I specify the document directory?

A: Locate the line `string dataDir = "YOUR DOCUMENT DIRECTORY";` in the code and replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

#### Q: How do I open an existing PDF document?

A: In Step 4, you'll open an existing PDF document using the `Document` constructor and providing the path to the input PDF file.

#### Q: Why is the font size adjusted?

A: Step 5 involves reducing the font size of text fragments by a factor of 0.7. This adjustment enhances readability and more accurately represents columnar text.

#### Q: How do I extract text from columns?

A: Step 6 consists of saving the modified PDF document to a memory stream, reloading it as a new document, and then using the `TextAbsorber` class to extract text from the columns.

#### Q: What is the purpose of saving the extracted text?

A: In Step 7, you'll save the extracted text to a text file at the specified output file path.

#### Q: Why reduce the font size before extraction?

A: Reducing the font size helps ensure that the extracted text aligns properly within the columns, providing a more accurate representation of the original layout.

#### Q: What is the key takeaway from this tutorial?

A: By following this tutorial, you've acquired the knowledge and skills needed to extract columns of text from a PDF document using Aspose.PDF for .NET. The resulting text has been saved to the specified output file.