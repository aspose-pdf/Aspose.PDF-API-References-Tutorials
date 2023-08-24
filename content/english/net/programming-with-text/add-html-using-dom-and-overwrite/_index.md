---
title: Add HTML Using DOM And PDF Overwrite
linktitle: Add HTML Using DOM And Overwrite
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add HTML content using DOM and PDF overwrite in Aspose.PDF for .NET.
type: docs
weight: 50
url: /net/programming-with-text/add-html-using-dom-and-overwrite/
---
This tutorial will guide you through the process of adding HTML content using DOM (Document Object Model) in Aspose.PDF for .NET. Additionally, you will learn how to overwrite styles for the HTML content. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to add the HTML content, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 3: Set the document directory and output file path
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 4: Create a new Document object
Instantiate a new `Document` object by adding the following line of code:

```csharp
Document doc = new Document();
```

## Step 5: Add a page to the document
Add a new page to the document by using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `page`.

```csharp
Page page = doc.Pages.Add();
```

## Step 6: Create an HtmlFragment with the HTML content
Instantiate an `HtmlFragment` object and provide the desired HTML content. In the provided code, the HTML content is assigned to the variable `title`. You can modify the HTML content as needed.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Step 7: Overwrite the styles for the HTML content
To overwrite the styles of the HTML content, you can modify the `TextState` properties of the `HtmlFragment` object. In the provided code, the font family is changed to "Arial" and the font size is set to 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Step 8: Set margin information
Adjust the bottom and top margins of the HTML fragment if necessary. In the provided code, the bottom margin is set to 10 and the top margin is set to 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Step 9: Add the HtmlFragment to the page
Add the `HtmlFragment` object to the paragraphs collection of the page.

```csharp
page.Paragraphs.Add(title);
```

## Step 10: Save the PDF document
Save the PDF document using the `Save` method of the `Document` object. Specify the output file path that you set in Step 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Add HTMLUsing DOMAnd Overwrite using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document object
Document doc = new Document();
// Add a page to pages collection of PDF file
Page page = doc.Pages.Add();
// Instantiate HtmlFragment with HTML contnets
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Font-family from 'Verdana' will be reset to 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Set bottom margin information
title.Margin.Bottom = 10;
// Set top margin information
title.Margin.Top = 400;
// Add HTML Fragment to paragraphs collection of page
page.Paragraphs.Add(title);
// Save PDF file
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Save PDF file
doc.Save(dataDir);
```

## Conclusion
You have successfully added HTML content using DOM in Aspose.PDF for .NET and overwritten the styles for the HTML content. The resulting PDF file can now be found at the specified output file path.

### FAQ's

#### Q: What is the focus of this tutorial?

A: This tutorial is designed to walk you through the process of adding HTML content to a PDF document using the Document Object Model (DOM) in Aspose.PDF for .NET. Additionally, you will learn how to overwrite styles for the HTML content, allowing you to customize its appearance. The tutorial provides C# source code snippets to demonstrate the required steps.

#### Q: Which namespaces do I need to import for this tutorial?

A: In the code file where you intend to add HTML content, import the following namespaces at the beginning of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: How do I specify the document directory and output file path?

A: In the code, locate the line `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

#### Q: How do I create a Document object?

A: In Step 4, you'll instantiate a new `Document` object using the following line of code:

```csharp
Document doc = new Document();
```

#### Q: How do I add a page to the document?

A: In Step 5, you'll add a new page to the document using the `Add` method of the `Pages` collection:

```csharp
Page page = doc.Pages.Add();
```

#### Q: How can I set HTML content using the DOM?

A: In Step 6, you'll create an `HtmlFragment` object and assign your desired HTML content to it. The HTML content is assigned to the variable `title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Q: How can I overwrite the styles of the HTML content?

A: In Step 7, you'll overwrite the styles of the HTML content by modifying the `TextState` properties of the `HtmlFragment` object. For example, you can change the font family to "Arial" and set the font size to 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Q: Can I adjust the margin of the HTML content?

A: Yes, in Step 8, you can adjust the bottom and top margins of the HTML fragment as needed:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Q: How do I add the HtmlFragment to the PDF document?

A: In Step 9, you'll add the `HtmlFragment` object (`title`) to the paragraphs collection of the page:

```csharp
page.Paragraphs.Add(title);
```

#### Q: How do I save the resulting PDF document?

A: After adding the HTML content and customizing its styles, use the `Save` method of the `Document` object to save the PDF document:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Q: What is the key takeaway from this tutorial?

A: By following this tutorial, you've successfully learned how to incorporate HTML content using the Document Object Model (DOM) in Aspose.PDF for .NET. Additionally, you've gained the ability to overwrite styles to tailor the appearance of the HTML content within the resulting PDF document.
