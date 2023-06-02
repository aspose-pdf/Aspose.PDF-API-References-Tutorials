---
title: Combo Box
linktitle: Combo Box
second_title: Aspose.PDF for .NET API Reference
description: Easily create combo box list in your PDF documents using Aspose.PDF for .NET.
type: docs
weight: 30
url: /net/programming-with-forms/combo-box/
---

In this tutorial, we will show you how to create a combo box list using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

First, make sure you have imported the necessary libraries and set the path to the documents directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a Document Object

Create a Document object to hold the PDF form:

```csharp
Document doc = new Document();
```

## Step 3: Add a page

Add a page to the document:

```csharp
doc.Pages.Add();
```

## Step 4: Instantiate a ComboBoxField Object

Instantiate a ComboBoxField object with the desired dimensions:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Step 5: Add options to the drop-down list

Add the desired options to the drop-down list:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Step 6: Add the combo box list to the form

Add the ComboBoxField object to the Document Form Fields collection:

```csharp
doc.Form.Add(combo);
```

## Step 7: Save the document

Save the PDF document:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Combo Box using Aspose.Words for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Create Document object
	Document doc = new Document();
	// Add page to document object
	doc.Pages.Add();
	// Instantiate ComboBox Field object
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Add option to ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Add combo box object to form fields collection of document object
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Save the PDF document
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

In this tutorial, we learned how to create a combo box list using Aspose.PDF for .NET. By following these steps, you can easily add a combo box list to your PDF documents using Aspose.PDF.
