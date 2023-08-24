---
title: Custom Tab Stops In PDF File
linktitle: Custom Tab Stops In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create custom tab stops in PDF file using Aspose.PDF for .NET.
type: docs
weight: 120
url: /ru/net/programming-with-text/custom-tab-stops/
---

This tutorial will guide you through the process of creating custom tab stops in PDF file using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to create custom tab stops, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Create a new Document instance
Instantiate a new `Document` object by adding the following line of code:

```csharp
Document _pdfdocument = new Document();
```

## Step 5: Add a page to the document
Add a new page to the document using the `Add` method of the `Pages` collection. In the provided code, the new page is assigned to the variable `page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Step 6: Create custom tab stops
Create a `TabStops` object and add custom tab stops to it. Set the alignment type and leader type for each tab stop.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Step 7: Create text fragments with tab stops
Create `TextFragment` objects and pass the custom tab stops to them. Use the special characters `#$TAB` to indicate the tab stops within the text.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Step 8: Save the PDF document
Save the PDF document using the `Save` method of the `Document` object.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Sample source code for Custom Tab Stops using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Conclusion
You have successfully created a PDF document with custom tab stops using Aspose.PDF for .NET. The resulting PDF file can now be found at the specified output file path.

### FAQ's

#### Q: What is the focus of this tutorial?

A: This tutorial is focused on guiding you through the process of creating custom tab stops in a PDF file using the Aspose.PDF for .NET library. The provided C# source code demonstrates the necessary steps to achieve this.

#### Q: Which namespaces should I import for this tutorial?

A: In the code file where you want to create custom tab stops, import the following namespaces at the beginning of the file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: How do I specify the document directory?

A: In the code, find the line `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

#### Q: How do I create a new Document instance?

A: In Step 4, you'll instantiate a new `Document` object using the provided code.

#### Q: How do I add a page to the document?

A: In Step 5, you'll add a new page to the document using the `Add` method of the `Pages` collection.

#### Q: How do I create custom tab stops?

A: In Step 6, you'll create a `TabStops` object and add custom tab stops to it. You'll also set alignment and leader types for each tab stop.

#### Q: How do I create text fragments with tab stops?

A: In Step 7, you'll create `TextFragment` objects and pass the custom tab stops to them. You'll use the special characters `#$TAB` to indicate the tab stops within the text.

#### Q: How do I save the PDF document?

A: In Step 8, you'll save the PDF document using the `Save` method of the `Document` object.

#### Q: What is the main takeaway from this tutorial?

A: By following this tutorial, you've learned how to create a PDF document with custom tab stops using Aspose.PDF for .NET. This can be useful for organizing and aligning text in a structured manner.