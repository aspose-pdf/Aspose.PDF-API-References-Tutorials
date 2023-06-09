---
title: Add Text Stamp
linktitle: Add Text Stamp
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily add a text stamp to your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 50
url: /net/programming-with-stamps-and-watermarks/add-text-stamp/
---
In this tutorial, we will take you step by step on how to add a text stamp to a PDF document using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to add a custom text stamp to a specific page of the PDF document.

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

