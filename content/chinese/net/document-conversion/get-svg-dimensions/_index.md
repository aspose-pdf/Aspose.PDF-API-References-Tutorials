---
title: 获取 SVG 尺寸
linktitle: 获取 SVG 尺寸
second_title: Aspose.PDF for .NET API 参考
description: 通过本分步指南了解如何使用 Aspose.PDF for .NET 将 SVG 文件转换为 PDF。非常适合希望操作 PDF 的开发人员。
type: docs
weight: 40
url: /zh/net/document-conversion/get-svg-dimensions/
---
## 介绍

欢迎来到 Aspose.PDF for .NET 的世界！如果您希望以编程方式操作 PDF 文件，那么您来对地方了。Aspose.PDF 是一个功能强大的库，允许开发人员轻松创建、编辑和转换 PDF 文档。无论您是经验丰富的开发人员还是刚刚起步，本指南都将引导您了解使用 Aspose.PDF for .NET 的基本知识，重点介绍如何获取 SVG 尺寸并将其转换为 PDF 格式。

## 先决条件

在我们进入代码之前，你需要做好以下几件事：

1. Visual Studio：确保您的计算机上安装了 Visual Studio。这是我们在本教程中使用的 IDE。
2.  .NET Framework：确保已安装 .NET Framework。Aspose.PDF 支持多个版本，因此请检查[文档](https://reference.aspose.com/pdf/net/)为了兼容性。
3.  Aspose.PDF 库：您可以从[下载链接](https://releases.aspose.com/pdf/net/)。如果你想先试用，你也可以获得[免费试用](https://releases.aspose.com/).
4. 基本 C# 知识：熟悉 C# 编程将帮助您更好地理解示例。

## 导入包

首先，您需要导入必要的软件包。操作方法如下：

1. 打开您的 Visual Studio 项目。
2. 在解决方案资源管理器中右键单击您的项目并选择“管理 NuGet 包”。
3. 搜索“Aspose.PDF”并安装该包。

一旦安装了该包，您就可以开始编码！

## 步骤 1：设置你的项目

### 创建新项目

首先，让我们在 Visual Studio 中创建一个新的 C# 项目。

- 打开 Visual Studio 并选择“创建新项目”。
- 选择“控制台应用程序（.NET Framework）”并单击“下一步”。
- 为您的项目命名（例如“AsposePDFExample”）并单击“创建”。

### 添加使用指令

现在你的项目已经设置好了，你需要在`Program.cs`文件：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

这将允许您访问 Aspose.PDF 库提供的类和方法。

## 步骤 2：加载 SVG 文档

### 定义文档目录

在加载 SVG 文档之前，您需要指定文档目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的 SVG 文件所在的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### 加载 SVG 文档

现在，让我们使用`SvgLoadOptions`类。该类允许您根据 SVG 内容调整页面大小。

```csharp
var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

## 步骤 3：调整页边距

为了确保 SVG 内容完美适合 PDF，您需要将页边距设置为零。此步骤对于保持 SVG 尺寸的完整性至关重要。

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

## 步骤 4：将文档保存为 PDF

最后，是时候将 SVG 文档保存为 PDF 了。您可以按如下方式指定输出文件名和路径：

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

就这样！您已成功使用 Aspose.PDF for .NET 将 SVG 文件转换为 PDF。

## 结论

恭喜！您刚刚使用 Aspose.PDF for .NET 完成了一项简单但功能强大的任务。通过遵循本指南，您已经学会了如何加载 SVG 文档、调整其边距并将其保存为 PDF。Aspose.PDF 的可能性无穷无尽，而这只是冰山一角。无论您是想创建复杂的 PDF、操作现有的 PDF 还是在格式之间进行转换，Aspose.PDF 都能满足您的需求。那么，您还在等什么？深入了解[文档](https://reference.aspose.com/pdf/net/)并探索这个图书馆提供的所有功能！

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个库，允许开发人员以编程方式创建、编辑和转换 PDF 文档。

### 如何安装 Aspose.PDF？
您可以通过 Visual Studio 中的 NuGet 包管理器安装 Aspose.PDF，或者从[地点](https://releases.aspose.com/pdf/net/).

### 我可以免费使用 Aspose.PDF 吗？
是的，Aspose 提供[免费试用](https://releases.aspose.com/)供您在购买之前测试该库。

### 在哪里可以找到对 Aspose.PDF 的支持？
您可以从[Aspose 论坛](https://forum.aspose.com/c/pdf/10).

### 如何获得 Aspose.PDF 的临时许可证？
您可以请求[临时执照](https://purchase.aspose.com/temporary-license/)来自 Aspose 网站。