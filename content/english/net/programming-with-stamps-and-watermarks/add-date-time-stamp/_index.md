---
title: Add Date Time Stamp In PDF File
linktitle: Add Date Time Stamp In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a date and time stamp to your PDF files using Aspose.PDF for .NET with this step-by-step guide. Perfect for enhancing document authenticity.
type: docs
weight: 10
url: /net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Introduction

When it comes to managing documents, especially PDFs, adding a date and time stamp can be a game-changer. Whether you’re working on legal documents, project reports, or invoices, a timestamp not only adds authenticity but also provides a clear record of when the document was created or modified. In this guide, we’ll walk you through the process of adding a date and time stamp to a PDF file using the Aspose.PDF library for .NET. 

This article is designed to be straightforward and easy to follow, so even if you’re new to programming or the Aspose.PDF library, you’ll be able to implement this feature with confidence. Let’s dive in!

## Prerequisites

Before we get started, there are a few prerequisites you need to have in place:

1. Visual Studio: Ensure you have Visual Studio installed on your machine. This is where you’ll write and execute your code.
2. Aspose.PDF for .NET: You need to download and install the Aspose.PDF library. You can find the latest version [here](https://releases.aspose.com/pdf/net/).
3. Basic Knowledge of C#: Familiarity with C# programming will help you understand the examples better, but don't worry if you're just starting out; we’ll explain everything step-by-step.
4. A PDF File: Have a sample PDF file ready. For our example, we’ll use a file named `AddTextStamp.pdf`.

Once you have these prerequisites, you’re ready to start adding date and time stamps to your PDF files!

## Import Packages

To begin, you need to import the necessary namespaces in your C# project. Here’s how to do it:

### Create a New Project

1. Open Visual Studio: Launch your Visual Studio application.
2. Create a New Project: Select “Create a new project” from the start screen.
3. Choose Console App: Select “Console App (.NET Framework)” from the list of project templates.
4. Name Your Project: Give your project a name, for example, `PDFDateTimeStamp`.

### Add Aspose.PDF Reference

1. Right-click on References: In the Solution Explorer, right-click on the “References” folder of your project.
2. Select “Add Reference”: Choose “Add Reference” from the context menu.
3. Browse for Aspose.PDF: Navigate to the location where you downloaded Aspose.PDF and select it. Click “OK” to add it to your project.

### Import Required Namespaces

At the top of your `Program.cs` file, you need to import the following namespaces:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Now that we have everything set up, let’s break down the process of adding a date and time stamp to a PDF file into clear, manageable steps.

## Step 1: Set the Document Directory

First, you need to specify the directory where your PDF file is located. This is crucial because the code will look for the PDF in this directory.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Replace with your actual path
```

Make sure to replace `YOUR DOCUMENT DIRECTORY` with the actual path to your PDF file.

## Step 2: Open the PDF Document

Next, you’ll open the PDF document where you want to add the timestamp. 

```csharp
// Open document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

This line of code initializes the `Document` class and loads your PDF file into the `pdfDocument` object.

## Step 3: Create the Date Time Stamp

Now it’s time to generate the date and time stamp. You’ll format it to display in a specific way. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

Here, `DateTime.Now` gets the current date and time, and `ToString` formats it to your desired format.

## Step 4: Create a Text Stamp

With the date and time string ready, you can now create a text stamp that will be added to your PDF.

```csharp
// Create text stamp
TextStamp textStamp = new TextStamp(annotationText);
```

This line creates a new instance of `TextStamp` using the formatted date and time string.

## Step 5: Set Properties of the Stamp

You can customize the appearance and position of the stamp. Here’s how to set its properties:

```csharp
// Set properties of the stamp
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

In this step, we set the margins and align the stamp to the bottom right corner of the PDF page.

## Step 6: Add the Stamp to the PDF

Now it’s time to add the text stamp to your PDF document. 

```csharp
// Adding stamp on stamp collection
pdfDocument.Pages[1].AddStamp(textStamp);
```

This line adds the stamp to the first page of the PDF. You can change the page number if you want to place it on a different page.

## Step 7: Create a Free Text Annotation (Optional)

If you want to add an annotation to the stamp, you can create a `FreeTextAnnotation` as follows:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

This optional step creates a free text annotation that can provide additional context or information about the stamp.

## Step 8: Configure the Annotation Border

If you want to customize the border of your annotation, you can do that as well:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

This code snippet sets the border width to 0, making it invisible, and adds the annotation to the PDF.

## Step 9: Save the PDF Document

Finally, you need to save the modified PDF document. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Specify the output file name
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

This line saves the PDF with the added timestamp to a new file. You can check your specified directory to see the output.

## Conclusion

Congratulations! You’ve successfully added a date and time stamp to a PDF file using Aspose.PDF for .NET. This simple yet effective feature can enhance your documents, making them more professional and providing a clear record of when they were created or modified. 

## FAQ's

### Can I customize the date format in the timestamp?
Yes, you can modify the `ToString` method to change the date format to your preference.

### Is Aspose.PDF free to use?
Aspose.PDF offers a free trial, but for full features, you need to purchase a license. You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Can I add multiple timestamps to a PDF?
Absolutely! You can create multiple `TextStamp` instances and add them to different pages or positions in the PDF.

### What if I don’t have Visual Studio?
You can use any C# IDE or text editor, but for running and debugging your project, Visual Studio is recommended.

### Where can I find more examples of using Aspose.PDF?
You can explore more examples and tutorials in the [Aspose.PDF documentation](https://reference.aspose.com/pdf/net/).
