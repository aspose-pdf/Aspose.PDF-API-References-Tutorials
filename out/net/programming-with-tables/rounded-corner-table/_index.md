---
title: Rounded Corner Table
linktitle: Rounded Corner Table
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create a rounded corner table in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 190
url: /content/net/programming-with-tables/rounded-corner-table/
---

In this tutorial, we will guide you step by step to create a rounded corner table in a PDF document using Aspose.PDF for .NET. We'll explain the provided C# source code and show you how to implement it.

## Step 1: Creating the table
First, we will create the table using the following code:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Step 2: Rounded Corner Style Setup
Next, we'll configure the rounded corner style for the table:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Step 3: Table Border Setup
To give the table a rounded corner border, we need to create a BorderInfo object and configure it with the appropriate parameters:

```csharp
// Create a GraphInfo object to set the border color
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Create an empty BorderInfo object
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Set the radius of the rounded border to 15
bInfo.RoundedBorderRadius = 15;

// Apply border information to the table
tab1.Border = bInfo;
```

### Example source code for Rounded Corner Table using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Create a blank BorderInfo object
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Set the border a rounder border where radius of round is 15
bInfo.RoundedBorderRadius = 15;
// Set the table Corner style as Round.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Set the table border information
tab1.Border = bInfo;
```

## Conclusion
Congratulation ! You have now learned how to create a rounded corner table in a PDF document using Aspose.PDF for .NET. This step-by-step guide showed you how to set up the rounded corner style and table border. Now you can apply this knowledge to your own projects.