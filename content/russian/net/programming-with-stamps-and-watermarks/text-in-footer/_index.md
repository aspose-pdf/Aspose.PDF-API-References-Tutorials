---
title: Text In Footer Of PDF File
linktitle: Text In Footer Of PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn to add text in the footer of PDF file with Aspose.PDF for .NET.
type: docs
weight: 180
url: /ru/net/programming-with-stamps-and-watermarks/text-in-footer/
---
In this tutorial, we are going to learn how to add text in the footer of PDF file using Aspose.PDF for .NET. Follow the steps below:

## Step 1: Project preparation

Make sure you have installed Aspose.PDF for .NET and created a C# project.

## Step 2: Importing namespaces

Add the following namespaces to your C# source file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 3: Opening the document

Open the existing PDF document using the path provided:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 4: Create footer text

Create a new text stamp with the text you want to add in the footer:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

You can customize the text by changing its properties like bottom margin, horizontal alignment, and vertical alignment.

## Step 5: Add footer text to all pages

Go through all the pages of the PDF document and add the text stamp in the footer:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Step 6: Saving the PDF Document

Once the footer text has been added on all pages, save the updated PDF document:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where you want to save the PDF document.

### Sample source code for Textin Footer using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Create footer
TextStamp textStamp = new TextStamp("Footer Text");

// Set properties of the stamp
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Add footer on all pages
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Save updated PDF file
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Conclusion

Congratulation ! You have learned how to add text in the footer of a PDF document using Aspose.PDF for .NET. You can now customize your footers by adding additional text to your PDF documents.

### FAQ's for text in footer of PDF file

#### Q: What is the purpose of adding text in the footer of a PDF document?

A: Adding text in the footer of a PDF document allows you to include important information, such as copyright notices, page numbers, document version, or any other text that you want to appear consistently at the bottom of each page.

#### Q: How does the provided C# source code achieve the addition of text in the footer of a PDF document?

A: The code demonstrates the process of opening an existing PDF document, creating a text stamp with the desired footer text, customizing the text properties, adding the text stamp to all pages, and finally saving the updated PDF document with the added footer text.

#### Q: Can I modify the appearance of the footer text, such as its font, size, color, and alignment?

A: Yes, you can customize the appearance of the footer text by modifying the properties of the `TextStamp` object. The code example includes setting properties like bottom margin, horizontal alignment, and vertical alignment. You can also adjust the font, size, color, and other text-related properties.

#### Q: Is it possible to add different text to each page's footer?

A: Yes, you can add different text to each page's footer by creating separate `TextStamp` objects with different text content or properties and then adding them to specific pages as needed.

#### Q: How do I ensure the footer text appears consistently on every page of the PDF document?

A: By using a loop that iterates through all the pages of the PDF document and adding the same text stamp to each page, you ensure that the footer text appears consistently on every page.

#### Q: Can I add multiple lines of text or format the footer text with line breaks?

A: Yes, you can add multiple lines of text to the footer by including line breaks in the text string. For example, you can use the escape sequence `\n` to indicate a line break in the text.

#### Q: What happens if I want to add different content to the header and footer of the same PDF document?

A: To add different content to the header and footer sections, you would follow similar steps for both sections. The code demonstrates adding text to the footer; you can use a similar approach to add text to the header.

#### Q: Is it possible to add images or other elements alongside the footer text using this approach?

A: While the provided code specifically demonstrates adding text to the footer, you can extend the approach to add other elements like images, lines, shapes, or any other content to the footer section using the Aspose.PDF library.