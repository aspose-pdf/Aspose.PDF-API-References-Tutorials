---
title: Set Expiry Date In PDF File
linktitle: Set Expiry Date In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set expiry date in PDF file using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 300
url: /de/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET is a powerful library that provides various features for working with PDF files. One such feature is the ability to set an expiry date for a PDF document. In this tutorial, we will walk you through the process of setting an expiry date for a PDF document using Aspose.PDF for .NET. 

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

## Conclusion

Setting an expiry date for a PDF document using Aspose.PDF for .NET is a useful feature to ensure that the document is only valid for a specified period. By following the step-by-step guide and using the provided C# source code, developers can easily set the expiry date and create PDFs with time-limited validity. This feature can be particularly helpful for documents that need to be accessed or distributed for a limited duration.

### FAQ's for set expiry date in PDF file

#### Q: Can I set a different expiry date for the PDF document?

A: Yes, you can set a different expiry date for the PDF document by modifying the JavaScript code in Step 5. In the provided example, the expiry date is set to May 2017. To set a different expiry date, you need to modify the `year` and `month` variables in the JavaScript code to the desired year and month.

#### Q: What happens when the PDF document has expired?

A: When the PDF document has expired, as specified in the JavaScript code, the viewer will display an alert message indicating that the file is expired and that the user needs a new one. This alert message will be shown when the PDF is opened.

#### Q: Can I use a specific time for the expiry date instead of just the date?

A: Yes, you can set a specific time for the expiry date in the JavaScript code. By modifying the `expiry` variable in the JavaScript code to include the desired time, you can set a specific time for the expiry date.