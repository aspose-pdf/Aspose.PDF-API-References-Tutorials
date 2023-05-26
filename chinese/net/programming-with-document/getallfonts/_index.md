---
title: 获取所有字体
linktitle: 获取所有字体
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南和示例代码，了解如何使用 Aspose.PDF for .NET 以编程方式获取 PDF 文档中使用的所有字体。
type: docs
weight: 160
url: /zh/net/programming-with-document/getallfonts/
---

Aspose.PDF for .NET 是一个功能强大的库，它使开发人员能够以编程方式处理 PDF 文档。它提供的功能之一是能够获取 PDF 文档中使用的所有字体。如果您需要以编程方式分析或操作 PDF 文档中的字体，这将很有用。

在本教程中，我们将讨论如何使用 Aspose.PDF for .NET 获取 PDF 文档中使用的所有字体。我们将提供有关如何执行此操作的分步指南以及示例源代码。

## 第 1 步：创建一个新的 C# 控制台应用程序
首先，在 Visual Studio 中创建一个新的 C# 控制台应用程序。您可以随意命名。创建项目后，您需要添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入 Aspose.PDF 命名空间
在 C# 文件的顶部添加以下代码行以导入 Aspose.PDF 命名空间：

```csharp
using Aspose.Pdf;
```

## 第 3 步：加载 PDF 文档
加载要从中获取字体的 PDF 文档：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第 4 步：获取所有字体
获取PDF文档中使用的所有字体：

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## 第 5 步：打印所有字体
打印 PDF 文档中使用的所有字体：

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### 使用 Aspose.PDF for .NET 获取所有字体的示例源代码
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## 结论
在本教程中，我们讨论了如何使用 Aspose.PDF for .NET 获取 PDF 文档中使用的所有字体。如果您需要以编程方式分析或操作 PDF 文档中的字体，获取 PDF 文档中使用的所有字体会很有用。 Aspose.PDF for .NET 提供了一个简单易用的 API 来处理 PDF 文档，包括获取 PDF 文档中使用的所有字体。


