---
title: 获取 SVG 尺寸
linktitle: 获取 SVG 尺寸
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 获取 SVG 尺寸的分步指南。
type: docs
weight: 40
url: /zh/net/document-conversion/get-svg-dimensions/
---

## 介绍
在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 获取 SVG 文件尺寸的过程。 SVG（可缩放矢量图形）是一种基于 XML 的图像格式，用于表示矢量图形。使用以下步骤，您将能够获取 SVG 文件的尺寸并将其另存为 PDF。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 SVG 文件
在此步骤中，我们将使用 Aspose.PDF for .NET 加载 SVG 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 SVG 文件所在的实际目录。

## 第二步：页面大小调整
现在我们已经加载了 SVG 文件，我们可以调整页面大小以适应 SVG 内容。使用以下代码：

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

上面的代码将页边距设置为零，允许页面大小根据 SVG 内容进行调整。

## 第 3 步：保存生成的 PDF
调整页面大小后，我们现在可以保存生成的 PDF 文档。这是最后一步：

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用要保存输出 PDF 文件的所需目录。
  
### 使用 Aspose.PDF for .NET 获取 SVG 尺寸的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 获取 SVG 文件尺寸的分步过程。按照上述说明，您现在应该能够获取 SVG 文件的尺寸并将它们保存为 PDF 格式。当您需要测量矢量图形的尺寸时，此功能会很有用。

