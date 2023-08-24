---
title: Text Segments In PDF File
linktitle: Text Segments In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search for specific text segments in PDF file using regular expressions in Aspose.PDF for .NET.
type: docs
weight: 540
url: /zh/net/programming-with-text/text-segments/
---
This tutorial explains how to search for specific text segments in PDF file using Aspose.PDF for .NET. The provided C# source code demonstrates different scenarios using regular expressions.

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

### FAQ's

#### Q: What is the purpose of the "Text Segments In PDF File" tutorial?

A: The "Text Segments In PDF File" tutorial aims to guide users on how to search for specific text segments within a PDF file using Aspose.PDF for .NET. The tutorial provides step-by-step instructions and C# code samples for performing text searches based on different scenarios using regular expressions.

#### Q: How does this tutorial help in searching for text segments in a PDF document?

A: This tutorial helps users understand how to utilize the Aspose.PDF for .NET library to search for specific text segments within a PDF document. By providing various code examples and regular expressions, users can customize their text search queries to find desired content within PDF files.

#### Q: What prerequisites are required to follow this tutorial?

A: Before starting the tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or install it in your project using NuGet.

#### Q: How do I set up my project to follow this tutorial?

A: To get started, create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library. This will allow you to leverage the library's functionality for working with PDF documents and text fragments.

#### Q: How can I search for specific text segments within a PDF file?

A: To search for specific text segments, you need to create a `TextFragmentAbsorber` object. The tutorial provides various code examples using regular expressions to demonstrate different search scenarios. By modifying the regular expressions, you can define your desired search patterns.

#### Q: What types of search scenarios are covered in the tutorial?

A: The tutorial covers a range of search scenarios using regular expressions, such as exact word matches, case-insensitive searches, searching for all strings within a document, finding text after specific strings, and searching for hyperlinks/URLs. The provided code examples can be customized to suit your specific search requirements.

#### Q: How do I process the search results after performing the text search?

A: After creating a `TextFragmentAbsorber` object and performing the search, you can process the search results based on your requirements. The tutorial focuses on demonstrating the search process itself, while how you process and utilize the search results depends on your project's needs.

#### Q: Can I use the provided code examples in my own projects?

A: Yes, you can use the provided code examples as a reference in your own C# projects. The examples demonstrate how to set up the search, define regular expressions, and perform text searches. You can adapt and integrate this code into your applications to search for specific text segments within PDF files.

#### Q: Where can I find the complete tutorial along with the sample code?

A: You can access the full tutorial and view the provided sample C# code by visiting the following link: [https://bit.ly/TextSegmentsTutorial](https://bit.ly/TextSegmentsTutorial)