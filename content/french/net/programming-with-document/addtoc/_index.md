---
title: Add TOC To PDF File
linktitle: Add TOC To PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a table of contents to PDF file using Aspose.PDF for .NET. Step-by-step guide with example source code. Boost document navigation!
type: docs
weight: 40
url: /fr/net/programming-with-document/addtoc/
---
In this tutorial, we will explore how to use the Add TOC (Table of Contents) to PDF file feature of Aspose.PDF for .NET to add a table of contents to PDF documents. We will provide a step-by-step guide and explain the C# source code required to achieve this. By the end of this tutorial, you will be able to generate a PDF document with a table of contents using Aspose.PDF for .NET.


## Step 1: Load the existing PDF file

To get started, we need to load an existing PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the following code with the actual path to your PDF file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Step 2: Create a new page for the table of contents

We will create a new page to hold the table of contents. The following code inserts a new page at index 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Step 3: Define the table of contents information

Next, we need to define the table of contents information. We will set the title and other properties of the table of contents. Add the following code:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Step 4: Create TOC elements

Now, we will create the elements of the table of contents. In this tutorial, we will create four TOC elements corresponding to different pages. Modify the following code as per your requirements:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Step 5: Save the updated document

Finally, we need to save the modified document with the table of contents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code below with the desired output file path:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Example source code for Adding TOC to PDF documents using Aspose.PDF for .NET

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load an existing PDF files
Document doc = new Document(dataDir + "AddTOC.pdf");

// Get access to first page of PDF file
Page tocPage = doc.Pages.Insert(1);

// Create object to represent TOC information
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Set the title for TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

// Create string objects which will be used as TOC elements
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Create Heading object
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Specify the destination page for heading object
	heading2.DestinationPage = doc.Pages[i + 2];

	// Destination page
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Destination coordinate
	segment2.Text = titles[i];

	// Add heading to page containing TOC
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Save the updated document
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, we explored how to add a table of contents (TOC) to PDF documents using Aspose.PDF for .NET. By following the step-by-step guide and utilizing the provided C# source code, you can easily generate a PDF document with a table of contents. The TOC enhances the document's usability, allowing users to navigate to specific sections or pages more efficiently. Aspose.PDF for .NET provides a robust and user-friendly solution for working with PDF files in .NET applications, enabling you to create dynamic and interactive PDF documents with ease.

### FAQ's for add TOC to PDF file

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that allows developers to work with PDF files in .NET applications effectively. It provides a wide range of features for creating, manipulating, and managing PDF documents programmatically.

#### Q: What is the purpose of adding a table of contents (TOC) to a PDF document?

A: The table of contents (TOC) provides a navigational aid for users, enabling them to quickly jump to specific sections or pages within the PDF document. It improves the document's usability and user experience.

#### Q: How do I add a table of contents to a PDF document using Aspose.PDF for .NET?

A: To add a table of contents to a PDF document using Aspose.PDF for .NET, you need to create a new page to hold the TOC, define the table of contents information, and then create TOC elements that correspond to specific pages or sections in the document.

#### Q: Can I customize the appearance of the table of contents?

A: Yes, you can customize the appearance of the table of contents by setting various properties of the TOC elements, such as font size, font style, and alignment. Aspose.PDF for .NET provides flexibility in designing the TOC to match your desired look and feel.

#### Q: Is Aspose.PDF for .NET suitable for adding advanced features to PDF documents?

A: Absolutely, Aspose.PDF for .NET is a feature-rich library that allows you to add advanced functionalities to PDF documents, including interactive elements, form fields, digital signatures, and more.