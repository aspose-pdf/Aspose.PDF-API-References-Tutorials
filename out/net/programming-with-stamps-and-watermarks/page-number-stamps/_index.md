---
title: Page Number Stamps
linktitle: Page Number Stamps
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add page number stamps to a PDF document with Aspose.PDF for .NET.
type: docs
weight: 160
url: /content/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
In this tutorial, we will guide you step by step on how to add page number stamps to a PDF document using Aspose.PDF for .NET. We'll use the provided C# source code to open an existing PDF document, create a page number stamp, set its properties, and add it to a specific page in the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Loading the existing PDF document

The first step is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the existing PDF document
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 3: Creating and Configuring the Page Numbering Stamp

Now that the PDF document is loaded, we can create a page numbering buffer and configure it according to our needs. Here's how:

```csharp
// Create a page number buffer
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Define if the buffer is in the background or not
pageNumberStamp.Background = false;

// Format of the page numbering buffer
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Bottom margin of page numbering buffer
pageNumberStamp.BottomMargin = 10;

// Horizontal alignment of the page numbering buffer
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Start number of page numbering
pageNumberStamp.StartingNumber = 1;

// Set page number buffer text properties
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

The above code creates a page number stamp with properties like page number format, bottom margin, horizontal alignment, starting number and text properties.

## Step 4: Adding the page number stamp to a specific page

Once the page number stamp is configured, we can add it to a specific page of the PDF document. Here's how:

```csharp
// Add the page number buffer to a specific page
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

The above code adds the page number stamp to the first page of the PDF document. You can change the page number as needed.

## Step 5: Saving the modified PDF document

Once the page number stamp is added to the PDF document, we can save the modified PDF document. Here's how:

```csharp
// Save the modified PDF document
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where you want to save the edited PDF document.

### Sample source code for Page Number Stamps using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Create page number stamp
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Whether the stamp is background
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Set text properties
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Add stamp to particular page
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Save output document
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusion

Congratulation ! You have learned how to add page number stamps to a PDF document using Aspose.PDF for .NET. You can now personalize your PDF documents by adding clear and informative page numbers.
