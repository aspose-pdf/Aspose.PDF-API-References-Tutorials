---
title: 获取水印
linktitle: 获取水印
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从您的 PDF 文档中提取水印。
type: docs
weight: 100
url: /zh/net/programming-with-stamps-and-watermarks/get-watermark/
---
在本教程中，我们将逐步向您介绍如何使用 Aspose.PDF for .NET 从 PDF 文档中获取水印。我们将向您展示如何使用提供的 C# 源代码循环访问特定页面的工件并获取水印类型、文本和位置。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：加载 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开 PDF 文档
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第三步：获取水印

现在您已经加载了 PDF 文档，您可以遍历特定的页面工件以获取水印信息。就是这样：

```csharp
//浏览工件并获取水印子类型、文本和位置
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

上面的代码遍历 PDF 文档第一页上的所有工件，并显示遇到的每个水印的子类型、文本和矩形（位置）。

### 使用 Aspose.PDF for .NET 获取水印的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

//遍历并获取工件的浴缸类型、文本和位置
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 从 PDF 文档中获取水印信息。现在您可以使用这些知识来分析和处理 PDF 文档中的水印。
