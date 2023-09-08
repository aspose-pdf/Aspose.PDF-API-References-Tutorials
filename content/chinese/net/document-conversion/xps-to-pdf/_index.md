---
title: XPS 转 PDF
linktitle: XPS 转 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 XPS 文件转换为 PDF 的分步指南。
type: docs
weight: 350
url: /zh/net/document-conversion/xps-to-pdf/
---
在本教程中，我们将逐步引导您了解如何使用 Aspose.PDF 库 for .NET 将 XPS 文件转换为 PDF。我们将详细介绍所提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。在本教程结束时，您将能够轻松地将 XPS 文件转换为 PDF 文档。

## 第1步：设置文档目录
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
代替`"YOUR DOCUMENTS DIRECTORY"`与您保存文件的路径。

## 步骤 2：使用 XPS 加载选项实例化 LoadOptions 对象
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
使用 XPS 加载选项创建 LoadOptions 对象的实例。

## 第 3 步：创建文档对象
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
创建指定输入 XPS 文件和加载选项的 Document 对象。

## 步骤 4：保存生成的 PDF 文档
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
将生成的 PDF 文档保存到指定目录。

### 使用 Aspose.PDF for .NET 将 XPS 转换为 PDF 的示例源代码

```csharp
try
{
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//使用 XPS 加载选项实例化 LoadOption 对象
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	//创建文档对象
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	//保存生成的 PDF 文档
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## 结论
在本教程中，我们学习了如何使用 .NET 的 Aspose.PDF 库将 XPS 文件转换为 PDF。通过按照提供的步骤操作，您可以在自己的应用程序中轻松执行此转换。将 XPS 文件转换为 PDF 时获得准确、专业的结果。

### 常见问题解答

#### 问：什么是 XPS，为什么我要将其转换为 PDF？

答：XPS（XML 纸张规范）是 Microsoft 开发的一种固定版式文档格式。将 XPS 转换为 PDF 可以使文档更易于访问和广泛兼容，因为 PDF 是跨不同平台和设备的普遍支持的格式。

#### 问：Aspose.PDF 库是否支持除 XPS 之外的其他文件格式？

答：是的，Aspose.PDF for .NET 支持各种其他文件格式的转换，例如 HTML、EPUB、SVG、XML 等。它还允许您以编程方式创建和操作 PDF 文档。

#### 问：我可以自定义 PDF 转换过程，例如设置页面大小、边距或其他选项吗？

答：是的，您可以使用 Aspose.PDF for .NET 自定义 PDF 转换过程。该库提供了多种选项来控制页面大小、边距、图像压缩、字体嵌入和其他 PDF 相关设置，以满足您的特定要求。

#### 问：是否有 Aspose.PDF for .NET 的试用版可供测试？

答：是的，您可以从 Aspose 官方网站下载并试用 Aspose.PDF for .NET 的试用版。试用版允许您在购买之前探索该库的功能。

#### 问：我可以批量将多个 XPS 文件转换为 PDF 吗？

答：是的，您可以通过实施循环或迭代 XPS 文件列表并使用提供的代码将每个文件转换为 PDF，以批处理方式将多个 XPS 文件转换为 PDF。