---
title: Get Document Window
linktitle: Get Document Window
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use the GetDocumentWindow feature of Aspose.PDF for .NET to retrieve information about a PDF document's window properties.
type: docs
weight: 170
url: /ar/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF for .NET is a powerful PDF manipulation library that allows developers to create, edit, and convert PDF files in their .NET applications. One of the features offered by this library is the ability to retrieve information about a document's window properties. This tutorial will guide you through the steps of using the `GetDocumentWindow` feature of Aspose.PDF for .NET to retrieve information about a PDF document's window properties.

## Step 1: Install Aspose.PDF for .NET

To use Aspose.PDF for .NET in your .NET applications, you must first install the library. You can download the latest version of the library from the [Aspose.PDF for .NET download page](https://releases.aspose.com/pdf/net).

Once you have downloaded the library, extract the contents of the ZIP file to a folder on your computer. You will then need to add a reference to the Aspose.PDF for .NET DLL in your .NET project.

## Step 2: Load the PDF Document

Once you have installed Aspose.PDF for .NET and added a reference to the DLL in your .NET project, you can begin using the `GetDocumentWindow` feature to retrieve information about a PDF document's window properties.

The first step in using this feature is to load the PDF document that you want to retrieve information about. To do this, you can use the following code:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

In the above code, replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your PDF document is located. This code will load the PDF document into a `Document` object, which you can then use to retrieve information about the document's window properties.

## Step 3: Retrieve the Document's Window Properties

To retrieve information about a PDF document's window properties, you can use the following code:

```csharp
// Retrieve the document's window properties
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

In the above code, each line retrieves a different window property of the PDF document and outputs it to the console. You can customize this code to retrieve only the properties that you are interested in.

### Example source code for get document window of PDF file using Aspose.PDF for .NET 

Here is the full source code for retrieving a PDF document's window properties using the `GetDocumentWindow` feature of Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Get different document properties
// Position of document's window - Default: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Predominant reading order; determins the position of page
// When displayed side by side - Default: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Whether window's title bar should display document title
// If false, title bar displays PDF file name - Default: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Whether to resize the document's window to fit the size of
// First displayed page - Default: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Whether to hide menu bar of the viewer application - Default: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// Whether to hide tool bar of the viewer application - Default: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Whether to hide UI elements like scroll bars
// And leaving only the page contents displayed - Default: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Document's page mode. How to display document on exiting full-screen mode.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// The page layout i.e. single page, one column
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// How the document should display when opened
// I.e. show thumbnails, full-screen, show attachment panel
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusion

In this tutorial, we have learned how to use Aspose.PDF for .NET to retrieve information about a PDF document's window properties. By loading a PDF document and accessing its window properties, you can gather information about how the document should be displayed when opened in a viewer application. Aspose.PDF for .NET provides a powerful set of features for working with PDF files programmatically, making it a valuable tool for PDF manipulation in .NET applications.

### FAQ's

#### Q: What is the purpose of retrieving a PDF document's window properties?

A: Retrieving a PDF document's window properties allows you to gather information about how the PDF document should be displayed when opened in a viewer application. These properties control various aspects such as window position, display mode, and visibility of UI elements.

#### Q: How can I install Aspose.PDF for .NET in my .NET project?

A: To install Aspose.PDF for .NET, you need to download the library from the [Aspose.PDF for .NET download page](https://releases.aspose.com/pdf/net). After downloading, extract the contents of the ZIP file and add a reference to the Aspose.PDF for .NET DLL in your .NET project.

#### Q: Can I customize the code to retrieve specific window properties only?

A: Yes, you can customize the code to retrieve specific window properties by commenting out the lines that you don't need. Each line in the code corresponds to a specific window property, so you can include or exclude properties based on your requirements.

#### Q: What types of window properties can I retrieve using Aspose.PDF for .NET?

A: Using Aspose.PDF for .NET, you can retrieve various window properties of a PDF document, including centering the window, setting the page layout, controlling the display of toolbars and menu bars, and more.