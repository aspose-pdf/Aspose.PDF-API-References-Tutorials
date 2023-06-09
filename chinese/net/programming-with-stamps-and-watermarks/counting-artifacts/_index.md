---
title: 计数工件
linktitle: 计数工件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松计算 PDF 文档中的水印。
type: docs
weight: 60
url: /zh/net/programming-with-stamps-and-watermarks/counting-artifacts/
---

在本教程中，我们将逐步介绍如何使用 Aspose.PDF for .NET 计算 PDF 文档中的伪影。我们将向您展示如何使用提供的 C# 源代码来计算 PDF 文档特定页面上的“水印”伪像的数量。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：加载 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 3 步：计算工件

现在您已经加载了 PDF 文档，您可以计算文档特定页面上的“水印”类型伪像。就是这样：

```csharp
//初始化计数器
int count = 0;

//遍历所有第一页工件
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     //如果工件子类型是“水印”，则增加计数器
     if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark)
         count++;
}

//显示“水印”类型工件的数量
Console.WriteLine("The page contains " + count + " watermarks");
```

上面的代码循环遍历 PDF 文档第一页上的所有工件，并为遇到的每个“水印”类型工件递增计数器。

### 使用 Aspose.PDF for .NET 计算工件的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

int count = 0;
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	//如果工件类型是水印，则创建计数器
	if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark) count++;
}
Console.WriteLine("Page contains " + count + " watermarks");

```

## 结论

恭喜！您学习了如何使用 Aspose.PDF for .NET 计算 PDF 文档中的“水印”伪像。您现在可以使用这些知识对 PDF 文档中的工件执行特定的分析和处理。
