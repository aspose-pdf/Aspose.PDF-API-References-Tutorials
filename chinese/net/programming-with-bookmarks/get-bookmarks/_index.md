---
title: 获取书签
linktitle: 获取书签
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松为您的 PDF 文件添加书签。
type: docs
weight: 70
url: /zh/net/programming-with-bookmarks/get-bookmarks/
---

从 PDF 文档中检索书签对于分析文档的结构和导航信息很有用。使用 Aspose.PDF for .NET，您可以通过以下源代码轻松获取书签：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要从中提取书签的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在我们将使用以下代码打开要从中提取书签的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
```

## 第 4 步：浏览书签

在此步骤中，我们将使用`foreach`环形。对于每个书签，我们都会显示标题、斜体样式、粗体样式和颜色等信息。下面是相应的代码：

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
}
```

### 使用 Aspose.PDF for .NET 获取书签的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
//循环遍历所有书签
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
}
```

## 结论

恭喜！现在，您有了使用 Aspose.PDF for .NET 获取书签的分步指南。您可以使用此代码解析书签并提取与 PDF 文档中每个书签相关的信息。

请务必查看官方 Aspose.PDF 文档以获取有关高级书签操作功能的更多信息。