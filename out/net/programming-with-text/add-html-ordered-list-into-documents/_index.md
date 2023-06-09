---
title: Add HTML Ordered List Into Documents
linktitle: Add HTMLOrdered List Into Documents
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add an HTML ordered list to a document using Aspose.PDF for .NET.
type: docs
weight: 30
url: /content/net/programming-with-text/add-html-ordered-list-into-documents/
---

In this tutorial, you will learn how to use the Aspose.PDF for .NET library to add an HTML ordered list into a document. The code provided demonstrates the necessary steps to accomplish this task.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to add the HTML ordered list, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 3: Set the document directory and output file path
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

Next, locate the line that says `string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` and replace `"AddHTMLOrderedListIntoDocuments_out.pdf"` with the desired name for your output PDF file.

## Step 4: Create a new Document object
Instantiate a new `Document` object by adding the following line of code:

```csharp
Document doc = new Document();
```

## Step 5: Create an HtmlFragment object with the HTML content
Instantiate an `HtmlFragment` object with the HTML content you want to add to the document. In the provided code, the HTML content is assigned to the variable `t`. You can modify the HTML content as needed.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Step 6: Add a page to the document
Add a new page to the document by using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `page`.

```csharp
Page page = doc.Pages.Add();
```

## Step 7: Add the HtmlFragment to the page
Add the `HtmlFragment` object to the page by using the `Add` method of the `Paragraphs` collection.

```csharp
page.Paragraphs.Add(t);
```

## Step 8: Save the PDF document
Save the resulting PDF file using the `Save` method of the `Document` object. Specify the output file path that you set in Step 3.

```csharp
doc.Save(outFile);
```

### Sample source code for Add HTMLOrdered List Into Documents using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// The path to the output document.  
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Instantiate Document object  
Document doc = new Document();
// Instantiate HtmlFragment object with corresponding HTML fragment  
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Add Page in Pages Collection  
Page page = doc.Pages.Add();
// Add HtmlFragment inside page  
page.Paragraphs.Add(t);
// Save resultant PDF file  
doc.Save(outFile);
```

## Conclusion
You have successfully added an HTML ordered list into a document using Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.

Remember to customize the HTML content and adjust the code according to your specific requirements.