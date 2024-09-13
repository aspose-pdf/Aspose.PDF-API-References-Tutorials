---
title: Get Document Window
linktitle: Get Document Window
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use the GetDocumentWindow feature of Aspose.PDF for .NET to retrieve information about a PDF document's window properties.
type: docs
weight: 170
url: /net/programming-with-document/getdocumentwindow/
---
# Introduction

Are you working with PDFs and want more control over how they appear when opened? Whether it’s hiding the menu bar or resizing the window to fit the first page, Aspose.PDF for .NET gives you all the tools you need to customize how a PDF behaves when opened in a viewer. In this tutorial, we’re going to break down how to retrieve and manipulate document window settings in Aspose.PDF for .NET.


# Prerequisites

Before diving into the tutorial, ensure that you have the following prerequisites in place:

- Aspose.PDF for .NET installed on your development environment.
  - [Download Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/)
- A valid license for Aspose.PDF, or you can get a [free trial](https://releases.aspose.com/) or [temporary license](https://purchase.aspose.com/temporary-license/).
- Basic understanding of .NET and C#.
- Visual Studio or another suitable IDE.

# Import Packages

Before you start writing any code, you’ll need to import the necessary packages. Open your project, and at the top of your C# file, add the following namespace:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

This will give you access to all the classes and methods needed for manipulating PDF documents using Aspose.PDF for .NET.

Now let’s break down the process of retrieving different document window settings. For this example, we’ll use a sample PDF file named `GetDocumentWindow.pdf`.

## Step 1: Set the Document Directory Path

First things first, we need to define the path to our PDF file. It’s crucial that you have the correct file path to avoid any errors during execution.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Here, replace `"YOUR DOCUMENT DIRECTORY"` with the actual directory where your PDF file is located. This is your working directory from where you will load the PDF document.

## Step 2: Open the PDF Document

Now that the file path is set, the next step is to open the PDF document using Aspose.PDF. This will load the document into memory, allowing you to retrieve its properties.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

With this simple line of code, you’ve successfully loaded your PDF file into the `pdfDocument` object, which will now allow you to access all its properties.

## Step 3: Retrieve Window Centering Status

Next, let’s check whether the document window should be centered when opened. The default value for this is `false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

If the output is `true`, the document’s window will open at the center of the screen. Otherwise, it will open at its default position.

## Step 4: Check Text Direction

Another crucial aspect of a PDF’s appearance is the text direction, which determines whether the text is read from left to right (L2R) or right to left (R2L). You can retrieve this information using the following code:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

The output will be `L2R` for left-to-right text and `R2L` for right-to-left text. This setting is especially useful for documents in languages like Arabic or Hebrew.

## Step 5: Display Document Title in Window

The next property allows you to control whether the document title or the file name should be displayed on the window’s title bar. By default, this is set to `false`, meaning the file name will be shown.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

If you want the document’s title to be displayed instead of the file name, this setting must be enabled.

## Step 6: Resize Window to Fit the First Page

Sometimes, you may want the document window to automatically resize itself to fit the first page of the PDF when it’s opened. Here’s how to check if that feature is enabled:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

By default, this is set to `false`, meaning the window size will remain as-is regardless of the first page’s size.

## Step 7: Hide the Menu Bar

For a more focused reading experience, you might want to hide the menu bar of the viewer application. You can retrieve this setting using the following line:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

This will return `true` if the menu bar is hidden, and `false` otherwise.

## Step 8: Hide the Tool Bar

Similarly, you might also want to hide the toolbar in the PDF viewer for a cleaner user interface. This setting can be retrieved as follows:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

If this setting is enabled, the toolbar will be hidden when the PDF is opened.

## Step 9: Hide the Scroll Bars and UI Elements

If you want to display only the page content without any additional UI elements like scroll bars, this setting controls that behavior:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

When set to `true`, the PDF viewer will hide scroll bars and other user interface elements, leaving only the document content.

## Step 10: Set Non-Full Screen Page Mode

You can control how the document appears when exiting full-screen mode using the `NonFullScreenPageMode` property. This setting is helpful for defining how the user should interact with the document in non-full screen mode.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

The output can be set to different modes like thumbnails, outlines, or attachments panel.

## Step 11: Define Page Layout

This setting allows you to control how the document pages are laid out. For instance, you can opt for a single page view or a continuous column view:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

This gives users flexibility in how they read or view the document content.

## Step 12: Specify Page Mode

Finally, the `PageMode` property defines how the document should be displayed when opened. Options include showing thumbnails, entering full-screen mode, or displaying the attachments panel.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

Depending on your needs, you can set this to any mode that suits your PDF’s purpose.

## Conclusion

As you can see, Aspose.PDF for .NET provides comprehensive tools to manipulate how your PDF documents are displayed in various PDF viewers. Whether you want to hide the toolbar, center the window, or control text direction, Aspose.PDF offers the flexibility to enhance the user’s viewing experience.

# FAQs

### Can I customize the initial zoom level of the PDF?
Yes, Aspose.PDF allows you to set the zoom level when the document is opened.

### How can I lock the window size of a PDF?
You can set the `FitWindow` property to prevent the window from resizing.

### Does Aspose.PDF support different reading modes?
Yes, it supports different modes like full-screen, thumbnails, and attachments.

### Is it possible to hide scroll bars in the PDF viewer?
Absolutely, you can hide scroll bars by setting the `HideWindowUI` property to `true`.

### Can I center the document window when opened?
Yes, you can control this by setting the `CenterWindow` property.
