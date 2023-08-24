---
title: Get Fields From Region In PDF File
linktitle: Get Fields From Region In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily get fields from a specific region in PDF file with Aspose.PDF for .NET.
type: docs
weight: 130
url: /it/net/programming-with-forms/get-fields-from-region/
---
In this tutorial, we will show you how to get the fields of a specific region in PDF file using Aspose.PDF for .NET. We will explain the C# source code step by step to guide you through this process.

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

### FAQ's

#### Q: Can I use this method to get fields from a non-rectangular region in a PDF document?

A: No, the provided method `GetFieldsInRect` is specifically designed to retrieve fields located within a rectangular region in a PDF document. If you need to extract fields from a non-rectangular region, you would need to implement custom logic to identify and extract the fields based on other criteria, such as field coordinates or names.

#### Q: How can I modify the size or position of the rectangle to get fields from a different region?

A: To get fields from a different region, you can modify the `Aspose.Pdf.Rectangle` object's parameters used to define the bounding rectangle. The `Rectangle` constructor takes four parameters: `x`, `y`, `width`, and `height`, which represent the top-left corner coordinates and the dimensions of the rectangle. Adjusting these parameters will change the region from which fields are extracted.

#### Q: What if there are no fields within the specified rectangular region?

A: If there are no fields within the specified rectangular region, the `GetFieldsInRect` method will return an empty array. You can check the length of the array to determine if there are any fields within the region.

#### Q: Can I get fields from overlapping regions in a PDF document?

A: Yes, you can get fields from overlapping regions in a PDF document by creating multiple `Aspose.Pdf.Rectangle` objects and calling the `GetFieldsInRect` method for each of them. Overlapping regions will be handled independently, and you will receive separate arrays of fields for each region.

#### Q: Is it possible to get fields from a specific page or multiple pages in the PDF document?

A: Yes, you can get fields from a specific page or multiple pages in a PDF document. To achieve this, you can load the PDF document, access the desired pages using the `doc.Pages` collection, and then apply the `GetFieldsInRect` method to each page's specific region.