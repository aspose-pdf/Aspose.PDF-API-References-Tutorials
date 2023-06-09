---
title: Text Segments
linktitle: Text Segments
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search for specific text segments within a PDF document using regular expressions in Aspose.PDF for .NET.
type: docs
weight: 540
url: /content/net/programming-with-text/text-segments/
---

This tutorial explains how to search for specific text segments within a PDF document using Aspose.PDF for .NET. The provided C# source code demonstrates different scenarios using regular expressions.

## Prerequisites

Before proceeding with the tutorial, make sure you have the following:

- Basic knowledge of C# programming language.
- Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or use NuGet to install it in your project.

## Step 1: Set up the project

Start by creating a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library.

## Step 2: Import necessary namespaces

Add the following using directives at the beginning of your C# file to import the required namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 3: Use TextFragmentAbsorber for text search

Create a `TextFragmentAbsorber` object to search for specific text segments using regular expressions:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Step 4: Perform text searches with regular expressions

Perform text searches based on different scenarios using regular expressions. Here are a few examples:

- To search for an exact word match: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- To search for a string in either upper case or lowercase: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- To search for all strings inside the PDF document: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- To find text after a specific string until a line break: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- To find text following a regex match: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- To search for Hyperlink/URLs inside the PDF document: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Replace the regular expressions with your desired search patterns.

## Step 5: Perform the search and process the results

Perform the search using the created `TextFragmentAbsorber` object and process the results based on your requirements.

### Sample source code for Text Segments using Aspose.PDF for .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// In order to search exact match of a word, you may consider using regular expression.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
// In order to search a string in either upper case or lowercase, you may consider using regular expression.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
// In order to search all the strings (parse all strings) inside PDF document, please try using following regular expression.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Find match of search string and get anything after the string till line break.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Please use following regular expression to find text following to the regex match.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// In order to search Hyperlink/URL's inside PDF document, please try using following regular expression.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Conclusion

Congratulations! You have successfully learned how to search for specific text segments within a PDF document using Aspose.PDF for .NET. This tutorial provided examples of different search scenarios using regular expressions. You can now incorporate this code into your own C# projects to search and process text segments in PDF files.