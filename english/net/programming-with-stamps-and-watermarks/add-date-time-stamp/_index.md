---
title: Add Date Time Stamp
linktitle: Add Date Time Stamp
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily add a date and time stamp to your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 10
url: /net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
In this article, we will take you step by step on how to add a date and time stamp using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to add a date and time stamp to an existing PDF document.

## Requirements

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 1: Setting up the environment

Before you can add a date and time stamp to a PDF document, you need to set up your development environment. Here are the steps to follow:

1. Open your favorite IDE (Integrated Development Environment).
2. Create a new C# project.
3. Make sure you have added a reference to the Aspose.PDF library for .NET.

## Step 2: Adding the Aspose.PDF library

The Aspose.PDF library for .NET is required to work with PDF documents in your project.

## Step 3: Loading the PDF document

The first step to adding a date and time stamp is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 4: Creating the date and time stamp

Now that you have uploaded the document

  PDF, you can create the date and time stamp to add. Here's how to do it:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Create a text buffer
TextStamp textStamp = new TextStamp(annotationText);
```

The code above creates a new text buffer containing the current date and time.

## Step 5: Configuring Stamp Properties

Before adding the stamp to the PDF document, you can configure various properties of the stamp, such as margin, horizontal and vertical alignment, etc. Here's how:

```csharp
// Set buffer properties
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

You can adjust these properties according to your needs.

## Step 6: Add Stamp to PDF

Now that the date and time stamp is ready, you can add it to a specific page of the PDF document. Here's how:

```csharp
// Add the stamp to the page's stamp collection
pdfDocument.Pages[1].AddStamp(textStamp);
```

The code above adds the stamp to the first page of the PDF document. You can specify another page if needed.

## Step 7: Save the output document

Once you have added the date and time stamp, you can save the modified PDF document. Here's how:

```csharp
// Save the output document
pdfDocument.Save(dataDir);
```

The above code saves the edited PDF document to the specified directory.

### Sample source code for Add Date Time Stamp using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Create text stamp
TextStamp textStamp = new TextStamp(annotationText);

// Set properties of the stamp
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Adding stamp on stamp collection
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Save output document
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Conclusion

Congratulation ! You have learned how to add a date and time stamp using Aspose.PDF for .NET. Now you can apply this knowledge to your own projects to add date and time stamps to PDF documents.

