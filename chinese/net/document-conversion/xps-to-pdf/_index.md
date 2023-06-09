---
title: XPS 转 PDF
linktitle: XPS 转 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 XPS 文件转换为 PDF 的分步指南。
type: docs
weight: 350
url: /zh/net/document-conversion/xps-to-pdf/
---

在本教程中，我们将逐步向您介绍如何使用 Aspose.PDF 库将 XPS 文件转换为 PDF。NET。我们将详细介绍所提供的 C# 源代码，并向您展示如何在您自己的项目中实施它。在本教程结束时，您将能够轻松地将 XPS 文件转换为 PDF 文档。

## 第一步：设置文件目录
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
代替`"YOUR DOCUMENTS DIRECTORY"`使用您保存文件的路径。

## 第 2 步：使用 XPS 加载选项实例化 LoadOptions 对象
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
使用 XPS 加载选项创建 LoadOptions 对象的实例。

## 第 3 步：创建文档对象
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
创建指定输入 XPS 文件和加载选项的文档对象。

## 第 4 步：保存生成的 PDF 文档
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
将生成的 PDF 文档保存到指定目录。

### 使用 Aspose.PDF for .NET 的 XPS 到 PDF 的示例源代码

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
在本教程中，我们学习了如何使用 .NET 的 Aspose.PDF 库将 XPS 文件转换为 PDF。按照提供的步骤，您可以在自己的应用程序中轻松执行此转换。将 XPS 文件转换为 PDF 时获得准确和专业的结果。