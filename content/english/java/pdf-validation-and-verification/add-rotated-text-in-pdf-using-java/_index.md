---
title: Add Rotated Text in PDF using Java
linktitle: Add Rotated Text in PDF using Java
second_title: Aspose.PDF Java PDF Processing API
description: Learn how to insert rotated text into a PDF document using Java. Follow this detailed step-by-step guide with code examples to enhance your PDFs with rotated text. 
type: docs
weight: 14
url: /java/pdf-validation-and-verification/add-rotated-text-in-pdf-using-java/
---

## Introduction

In this comprehensive tutorial, we will delve into the process of adding rotated text to a PDF document using Java. Whether you need to label diagrams, create watermarks, or add special effects to your PDFs, this guide will walk you through the steps. We'll use Aspose.PDF for Java, a powerful library for PDF manipulation, to demonstrate the process.

## Prerequisites

Before we get started, ensure you have the following prerequisites in place:

1. Java Development Environment: Make sure you have Java installed on your system.

2. Aspose.PDF for Java: Download and include the Aspose.PDF library in your Java project. You can find the download link [here](https://releases.aspose.com/pdf/java/).

## Step 1: Create a New PDF Document

Let's begin by creating a new PDF document using Aspose.PDF. This document will serve as the canvas for our rotated text.

```java
// Initialize the PDF document
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## Step 2: Add a Page

Next, add a page to the PDF document where you want to insert the rotated text:

```java
// Add a new page to the document
com.aspose.pdf.Page page = pdfDocument.getPages().add();
```

## Step 3: Define Rotated Text

Now, let's define the text that you want to insert and rotate. You can customize the text, font, and rotation angle as per your requirements:

```java
// Define the text content
String text = "Rotated Text Example";

// Create a TextFragment object
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// Set the font size and style
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// Define the rotation angle (in degrees)
textFragment.setTextRotation(45);
```

In this example, we've set the text to "Rotated Text Example," chosen the Arial font, set the font size to 12, and rotated the text by 45 degrees. Adjust these parameters to match your specific requirements.

## Step 4: Position the Rotated Text

Specify the position on the page where you want to place the rotated text:

```java
// Set the position of the text
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

Here, we've positioned the text at coordinates (100, 200) on the page. Modify these coordinates to place the text precisely where you need it.

## Step 5: Add Rotated Text to the Page

Now, add the rotated text to the page:

```java
// Add the rotated text to the page
page.getParagraphs().add(textFragment);
```

## Step 6: Save the PDF

Finally, save the PDF document with the rotated text:

```java
// Save the PDF document
pdfDocument.save("output.pdf");
```

## Conclusion

In this tutorial, we've explored the process of adding rotated text to a PDF document using Java and Aspose.PDF for Java. You've learned how to create a new PDF, define rotated text with custom styles, position it on the page, and save the modified PDF.

Rotated text can be a valuable addition to your PDFs for various purposes, such as labeling diagrams, watermarking, or adding creative elements to your documents.

Enhance your PDF documents by incorporating rotated text with ease, thanks to the capabilities of Aspose.PDF for Java.

---

## FAQs (Frequently Asked Questions)

### 1. Can I rotate text by different angles in the same PDF?
   Yes, you can add multiple instances of rotated text with different angles to the same PDF document. Simply repeat the process described in this tutorial for each piece of rotated text.

### 2. How can I change the color of the rotated text?
   To change the text color, use the `textFragment.getTextState().setForegroundColor` method and specify the color in RGB format. For example, to set the text color to red, use `textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. Is Aspose.PDF for Java a free library?
   Aspose.PDF for Java is a powerful commercial library, but it offers a free trial version for testing and evaluation. Depending on your project's requirements, you can choose an appropriate licensing option.

### 4. Can I rotate text by 90 degrees to create vertical text?
   Yes, you can rotate text by 90 degrees to create vertical text. Simply set the rotation angle to 90 degrees, and the text will appear vertically on the page.

### 5. Are there other libraries for working with PDFs in Java?
   Yes, several libraries, such as iText and PDFBox, are available for PDF manipulation in Java. Each library has its unique features and capabilities, so choose the one that best suits your project's needs.
