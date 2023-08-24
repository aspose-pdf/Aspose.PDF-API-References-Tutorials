---
title: Add Text Stamp In PDF File
linktitle: Add Text Stamp In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily add a text stamp in PDF file with Aspose.PDF for .NET.
type: docs
weight: 50
url: /tr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
In this tutorial, we will take you step by step on how to add a text stamp in PDF file using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to add a custom text stamp to a specific page of the PDF file.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Loading the PDF document

The first step is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 3: Creating the text buffer

Now that you have uploaded the PDF document, you can create the text stamp to add. Here's how to do it:

```csharp
// Create the text buffer
TextStamp textStamp = new TextStamp("Example Stamp");
```

The code above creates a new text buffer containing the specified text.

## Step 4: Configuring Text Stamp Properties

Before adding the text stamp to the PDF document, you can configure various properties of the stamp, such as background, position, rotation, font, size, etc. Here's how:

```csharp
// Configure text buffer properties
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

You can adjust these properties according to your needs.

## Step 5: Add Text Stamp to PDF

Now that the text stamp is ready, you can add it to a specific page of the PDF document. Here's how:

```csharp
// Add text buffer to specific page
pdfDocument.Pages[1].AddStamp(textStamp);
```

The code above adds the text stamp to the first page of the PDF document. You can specify another page if needed.

## Step 6: Save the output document

Once you have added the text stamp, you can save the edited PDF document. Here's how:

```csharp
// Save the output document
pdfDocument.Save(dataDir);
```

The code above saves the modified PDF document in the specified directory.

### Sample source code for Add Text Stamp using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Create text stamp
TextStamp textStamp = new TextStamp("Sample Stamp");

// Set whether stamp is background
textStamp.Background = true;

// Set origin
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Rotate stamp
textStamp.Rotate = Rotation.on90;

// Set text properties
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Add stamp to particular page
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Save output document
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusion

Congratulation ! You have learned how to add a text stamp using Aspose.PDF for .NET. Now you can apply this knowledge to your own projects to add custom text stamps to PDF documents.

### FAQ's for add text stamp in PDF file

#### Q: What is the purpose of adding a text stamp in a PDF file using Aspose.PDF for .NET?

A: Adding a text stamp allows you to place custom text on a specific page of a PDF document. This feature is useful for adding labels, comments, watermarks, or any other textual information to enhance the document's content and provide additional context.

#### Q: Can I customize the appearance of the text stamp, such as font, size, color, and rotation?

A: Yes, you can fully customize the appearance of the text stamp. The provided C# source code demonstrates how to set various properties of the `TextStamp` object, including font, font size, font style, text color, background color, and rotation.

#### Q: Is it possible to add multiple text stamps to different pages of the same PDF document?

A: Absolutely, you can add multiple text stamps to different pages of the same PDF document. The tutorial's provided code allows you to specify the target page for adding the text stamp, making it versatile for different pages within the document.

#### Q: How do I specify the position of the text stamp within the PDF document?

A: You can customize the position of the text stamp by modifying the `XIndent` and `YIndent` properties of the `TextStamp` object. These properties define the coordinates of the stamp's top-left corner relative to the origin of the page.

#### Q: Can I apply this method to existing PDF documents to add text stamps?

A: Yes, you can apply this method to existing PDF documents to add text stamps. The tutorial's provided code demonstrates how to load an existing PDF document and add a text stamp to a specific page.

#### Q: Can I add both background and foreground colors to the text stamp?

A: Yes, you can add both background and foreground colors to the text stamp. By setting the `Background` property to `true`, you can provide a colored background for the text stamp. Additionally, you can set the `TextState.ForegroundColor` property to specify the color of the text itself.

#### Q: How can I ensure that the text stamp does not obscure the underlying content of the PDF document?

A: When adding a text stamp, be mindful of its placement to ensure that it does not obstruct critical information or negatively affect the document's readability. You can adjust the `XIndent` and `YIndent` properties to position the text stamp appropriately.

#### Q: Can I use this method to add stamps other than text, such as images or logos?

A: This specific tutorial focuses on adding text stamps, but you can similarly add other types of stamps, such as images or logos, using Aspose.PDF for .NET. The process involves creating the appropriate stamp object and configuring its properties.

#### Q: How can I automate the process of adding text stamps to multiple PDF documents?

A: You can automate the process of adding text stamps to multiple PDF documents by creating a script or program that iterates through a list of documents and applies the same text stamping process to each one.