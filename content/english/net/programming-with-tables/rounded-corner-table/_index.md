---
title: Rounded Corner Table In PDF Document
linktitle: Rounded Corner Table In PDF Document
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create a beautiful rounded corner table in your PDF documents using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 190
url: /net/programming-with-tables/rounded-corner-table/
---
## Introduction

Creating visually appealing documents is crucial, especially when you want to convey information in a more engaging way. One cute trick is using rounded corners in tables within PDF files! With Aspose.PDF for .NET, this is not only feasible but also pretty straightforward. In this guide, I will walk you through the process step-by-step. You’ll not just learn how to create rounded corner tables, but also how to utilize other features of Aspose seamlessly.

## Prerequisites

Before we begin our adventure into rounded corner tables, there are a few things you need to have in place:

1. Visual Studio: Ensure you have Visual Studio installed on your machine. This will be your playground for coding and testing.
2. .NET Framework: Make sure you're using a relevant version of the .NET Framework compatible with Aspose.PDF.
3. Aspose.PDF for .NET: You need the Aspose.PDF library. You can download it from the [Aspose releases page](https://releases.aspose.com/pdf/net/).
4. A suitable IDE: While Visual Studio is preferred, any other IDE supporting C# can do the job.
5. Basic C# knowledge: Understanding the basics of C# programming will help you grasp the content faster.

Got all that ready? Great! Let’s move ahead.

## Import Packages

Alright, let’s start by importing all the necessary packages before we get into the coding action. 

### Open Your Project

First things first, fire up your Visual Studio, and create a new project. You can choose a Console Application for this tutorial since it keeps things simple.

### Add Aspose.PDF to Your Project

Once your project is set up:
- Right-click on the project in the Solution Explorer.
- Select “Manage NuGet Packages.”
- Search for `Aspose.PDF` and install it.

Now you’re ready to go!

### Import Aspose.PDF Namespace

At the top of your `Program.cs` or wherever your main code resides, you’ll want to add:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

This gives you access to all the cool features of the Aspose.PDF library.

Alright, let’s roll up our sleeves and get to the fun part - creating our rounded corner table! Below, I’ll break down each step for you.

## Step 1: Set the Directory

To start, you need to set the path for where your PDF file will be stored. This is where you’ll instruct your code to create the PDF document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Change `YOUR DOCUMENT DIRECTORY` to the actual path where you want your PDF saved. 

## Step 2: Initialize the Document

With the directory set, the next step is to create a new PDF document. This is like laying the foundation of a house – everything else will build on top of this.

```csharp
Document pdfDocument = new Document();
```

## Step 3: Create a Table

Now it’s time to create the star of the show: the table.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

This line sets up a new table object ready for some magic!

## Step 4: Create Border Information

To give your table a nice outline and the effect of rounded corners, you need to create an instance of `BorderInfo`.

```csharp
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red; // Set your preferred color
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
```

Here we defined the border and set its color to red. You can pick any color you fancy!

## Step 5: Set Rounded Border Radius

Now, let’s give those corners some character by rounding them off.

```csharp
bInfo.RoundedBorderRadius = 15; // Adjust the radius as needed
```

A radius of 15 will give a noticeable rounded effect. Feel free to tweak this number to suit your style.

## Step 6: Round the Table Corners

Next, you tell the table to use the rounded corners you’ve just defined.

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

With this line, your table is officially in the round corner club!

## Step 7: Apply the Border to the Table

Let’s wrap everything together by applying the border information to your table.

```csharp
tab1.Border = bInfo;
```

Boom! Your table now has a border with rounded corners.

## Step 8: Add the Table to the PDF Document

So far, we’ve got everything set up. Now, let’s add the table to the document.

```csharp
pdfDocument.Pages.Add().Paragraphs.Add(tab1);
```

This line takes the table and adds it to a new page in your PDF. 

## Step 9: Save the Document

The last step in our journey is saving the PDF document. 

```csharp
pdfDocument.Save(dataDir + "RoundedCornerTable.pdf");
```

Here, you’ll save it in the specified directory with the name "RoundedCornerTable.pdf".

## Conclusion

And there you have it! You’ve successfully created a rounded corner table in a PDF document using Aspose.PDF for .NET. This simple yet effective design can go a long way in making your documents visually appealing. Don’t hesitate to experiment with colors, styles, and additional features offered by Aspose.PDF to further enhance your documents.

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a library that allows .NET applications to create and manipulate PDF documents easily.

### Can I use Aspose.PDF for free?
Yes! You can try Aspose.PDF with a free trial available on their [release page](https://releases.aspose.com/).

### What are rounded corner tables useful for?
They enhance the visual appeal of tables in PDF documents, making them more engaging for readers.

### Where can I buy Aspose.PDF?
You can purchase it directly from the [Aspose purchase page](https://purchase.aspose.com/buy).

### What if I need support?
For assistance, you can visit the Aspose support forums at [Aspose Support](https://forum.aspose.com/c/pdf/10).
