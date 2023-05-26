---
title: Set Expiry Date
linktitle: Set Expiry Date
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set expiry date in PDF documents using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 300
url: /net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET is a powerful library that provides various features for working with PDF files. One such feature is the ability to set an expiry date for a PDF document. In this tutorial, we will walk you through the process of setting an expiry date for a PDF document using Aspose.PDF for .NET. 

## Outline
1. What is Aspose.PDF for .NET?
2. Set Expiry Date Feature of Aspose.PDF for .NET
3. Setting Up the Environment
4. Creating a New PDF Document
5. Adding a Page to the PDF Document
6. Adding Text to the PDF Document
7. Creating a JavaScript Object to Set PDF Expiry Date
8. Setting JavaScript as PDF Open Action
9. Saving the PDF Document
10. Example Source Code for Set Expiry Date using Aspose.PDF for .NET
11. Conclusion
12. FAQs

## Step 1: Set the path to the document directory

Before we start, we need to set the path to the directory where our PDF document is located. We will store this path in a variable called "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Creating a new PDF document

To create a new PDF document, we need to instantiate a new `Aspose.Pdf.Document` object. We can do this using the following code:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Step 3: Adding a new page to the PDF document

Once we have created the PDF document, we can add a new page to it. We can do this using the following code:

```csharp
doc.Pages.Add();
```

## Step 4: Adding Text to the PDF Document

After adding a page to the PDF document, we can add text to it using the `Paragraphs` collection. We can do this using the following code:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Step 5: Setting PDF expiry date using JavaScript

To set the PDF expiry date, we need to create a JavaScript object. We can do this using the following code:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Set JavaScript as PDF open action
doc.OpenAction = javaScript;
```

In this code, we are setting the expiry date to May 2017.

## Step 6: Save the PDF File

After you've set the expiry date, you need to save the PDF file. To do this, you can use the `Save` method of the `Document` object and pass in the path to where you want to save the updated PDF file.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Save PDF Document
doc.Save(dataDir);
```

### Example source code for Set Expiry Date using Aspose.PDF for .NET

Here's the complete example source code for setting expiry date using Aspose.PDF for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instantiate Document object
	Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
	// Add page to pages collection of PDF file
	doc.Pages.Add();
	// Add text fragment to paragraphs collection of page object
	doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
	// Create JavaScript object to set PDF expiry date
	JavascriptAction javaScript = new JavascriptAction(
	"var year=2017;"
	+ "var month=5;"
	+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
	+ "expiry = new Date(year, month);"
	+ "if (today.getTime() > expiry.getTime())"
	+ "app.alert('The file is expired. You need a new one.');");
	// Set JavaScript as PDF open action
	doc.OpenAction = javaScript;

	dataDir = dataDir + "SetExpiryDate_out.pdf";
	// Save PDF Document
	doc.Save(dataDir);
	
```

