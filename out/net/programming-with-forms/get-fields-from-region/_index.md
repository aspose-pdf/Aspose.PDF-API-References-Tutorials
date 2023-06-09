---
title: Get Fields From Region
linktitle: Get Fields From Region
second_title: Aspose.PDF for .NET API Reference
description: Easily get fields from a specific region into your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 130
url: /content/net/programming-with-forms/get-fields-from-region/
---

In this tutorial, we will show you how to get the fields of a specific region in a PDF document using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

## Step 1: Preparation

Make sure you have imported the necessary libraries and set the path to your documents directory:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF file

Open the PDF file:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Step 3: Create a rectangle object to bound the region

Create a rectangle object to bound the region where you want to get the fields:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Step 4: Obtain the PDF form

Get the PDF form of the document:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Step 5: Get the fields in the rectangular region

Get the fields located in the specified rectangular region:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Step 6: Display field names and values

Iterate through the resulting fields and display their names and values:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Sample source code for Get Fields From Region using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open pdf file
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Create rectangle object to get fields in that area
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Get the PDF form
Aspose.Pdf.Forms.Form form = doc.Form;
// Get fields in the rectangular area
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Display Field names and values
foreach (Field field in fields)
{
	// Display image placement properties for all placements
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusion

In this tutorial, we learned how to get the fields of a specific region in a PDF document using Aspose.PDF for .NET. By following these steps, you can easily extract the fields located in a given rectangular area of your PDF document using Aspose.PDF.