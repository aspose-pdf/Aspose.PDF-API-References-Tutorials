---
title: Embed Fonts In PDF File With Subset Strategy
linktitle: Embed Fonts With Subset Strategy
second_title: Aspose.PDF for .NET API Reference
description: Learn how to embed fonts in a PDF file with Subset Strategy using Aspose.PDF for .NET. Optimize your PDF size by embedding only necessary characters.
type: docs
weight: 130
url: /ru/net/programming-with-document/embedfontsusingsubsetstrategy/
---
In this tutorial, we will discuss how to embed fonts in a PDF file with a subset strategy using Aspose.PDF for .NET. Aspose.PDF for .NET is a powerful library that allows developers to create, edit, and manipulate PDF documents programmatically. Embedding fonts in a PDF file is an important step to ensure that the document is displayed correctly on different devices, regardless of whether the required fonts are installed on those devices or not.

## Step 1: Create a new C# Console Application
To get started, create a new C# Console Application in Visual Studio. You can name it whatever you like. Once the project is created, you need to add a reference to the Aspose.PDF for .NET library.

## Step 2: Import the Aspose.PDF Namespace
Add the following line of code at the top of your C# file to import the Aspose.PDF namespace:

```csharp
using Aspose.Pdf;
```

## Step 3: Load an Existing PDF File
To embed fonts in an existing PDF file, you need to load that file using the Document class. The following code demonstrates how to load an existing PDF file:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load an existing PDF file
Document doc = new Document(dataDir + "input.pdf");
```

## Step 4: Embed Fonts with Subset Strategy
Aspose.PDF for .NET provides two strategies for font embedding: SubsetAllFonts and SubsetEmbeddedFontsOnly.

The SubsetAllFonts strategy will embed all fonts in the document as a subset. A subset is a portion of the font that contains only the characters used in the document. This strategy is useful for reducing the file size of the PDF document.

The SubsetEmbeddedFontsOnly strategy will embed only the subset of fonts that are already embedded in the document. If a font is not embedded, it will not be affected by this strategy.

The following code demonstrates how to embed fonts in a PDF file with a subset strategy:

```csharp
// All fonts will be embedded as subset into document in case of SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Font subset will be embedded for fully embedded fonts but fonts which are not embedded into document will not be affected.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Step 5: Save the PDF Document
Once you have embedded all the fonts in the PDF file with a subset strategy, you need to save the document. The following code demonstrates how to save the PDF file:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Example source code for embeding fonts with subset strategy using Aspose.PDF for .NET. 

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// All fonts will be embedded as subset into document in case of SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// Font subset will be embedded for fully embedded fonts but fonts which are not embedded into document will not be affected.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Conclusion
In this article, we have discussed how to embed fonts in a PDF file with a subset strategy using Aspose.PDF for .NET. Aspose.PDF for .NET provides a simple and easy-to-use API to work with PDF documents, including adding and embedding fonts with different strategies. Embedding fonts in a PDF file is an important step to ensure that the document is displayed correctly on different devices, and the subset strategy is a useful feature to reduce the file size of the PDF document.

### FAQ's for embed fonts in PDF file with subset strategy

#### Q: What is a subset strategy for font embedding in a PDF file?

A: A subset strategy for font embedding in a PDF file means that only a portion of the font containing the characters used in the document will be embedded. This helps reduce the file size of the PDF document by eliminating unnecessary font data.

#### Q: What is the difference between SubsetAllFonts and SubsetEmbeddedFontsOnly strategies?

A: The `SubsetAllFonts` strategy will embed all fonts in the document as a subset, while the `SubsetEmbeddedFontsOnly` strategy will only embed the subset of fonts that are already embedded in the document. The latter strategy will not affect fonts that are not already embedded.

#### Q: Why is font embedding with a subset strategy important?

A: Font embedding with a subset strategy is important to ensure that the PDF file contains the necessary font data for displaying text correctly, while also keeping the file size smaller by including only the characters used in the document.

#### Q: Can I use Aspose.PDF for .NET to embed fonts with different strategies?

A: Yes, Aspose.PDF for .NET provides various strategies for font embedding, including `SubsetAllFonts` and `SubsetEmbeddedFontsOnly`. You can choose the appropriate strategy based on your requirements.

#### Q: Is Aspose.PDF for .NET a reliable library for working with PDF documents?

A: Yes, Aspose.PDF for .NET is a reliable and powerful library for working with PDF documents. It provides extensive features for creating, editing, and manipulating PDF files in .NET applications.