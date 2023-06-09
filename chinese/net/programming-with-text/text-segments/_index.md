---
title: 文本片段
linktitle: 文本片段
second_title: Aspose.PDF for .NET API 参考
description: 了解如何在 Aspose.PDF for .NET 中使用正则表达式搜索 PDF 文档中的特定文本段。
type: docs
weight: 540
url: /zh/net/programming-with-text/text-segments/
---

本教程解释了如何使用 Aspose.PDF for .NET 在 PDF 文档中搜索特定文本段。提供的 C# 源代码演示了使用正则表达式的不同场景。

## 先决条件

在继续本教程之前，请确保您具有以下内容：

- C# 编程语言的基础知识。
- 安装了 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

## 第 1 步：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入必要的命名空间

在 C# 文件的开头添加以下 using 指令以导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第 3 步：使用 TextFragmentAbsorber 进行文本搜索

创建一个`TextFragmentAbsorber`使用正则表达式搜索特定文本段的对象：

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## 第 4 步：使用正则表达式执行文本搜索

使用正则表达式根据不同场景执行文本搜索。这里有一些例子：

- 要搜索完全匹配的单词： 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- 要搜索大写或小写的字符串： 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- 要搜索 PDF 文档中的所有字符串： 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- 要查找特定字符串之后直到换行符的文本： 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- 要查找正则表达式匹配后的文本： 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- 要在 PDF 文档中搜索超链接/URL： 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

用您想要的搜索模式替换正则表达式。

## 第 5 步：执行搜索并处理结果

使用创建的执行搜索`TextFragmentAbsorber`根据您的要求反对和处理结果。

### 使用 Aspose.PDF for .NET 的文本片段示例源代码 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
//为了搜索单词的精确匹配，您可以考虑使用正则表达式。
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
//为了以大写或小写形式搜索字符串，您可以考虑使用正则表达式。
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
//为了搜索 PDF 文档中的所有字符串（解析所有字符串），请尝试使用以下正则表达式。
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
//查找搜索字符串的匹配项并获取字符串之后的任何内容，直到换行符。
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
//请使用以下正则表达式查找正则表达式匹配后的文本。
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
//为了在 PDF 文档中搜索超链接/URL，请尝试使用以下正则表达式。
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## 结论

恭喜！您已经成功学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中搜索特定文本段。本教程提供了使用正则表达式的不同搜索场景的示例。您现在可以将此代码合并到您自己的 C# 项目中，以搜索和处理 PDF 文件中的文本段。