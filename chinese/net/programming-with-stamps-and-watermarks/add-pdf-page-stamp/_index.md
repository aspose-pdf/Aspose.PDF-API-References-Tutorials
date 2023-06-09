---
title: 添加 PDF 页面标记
linktitle: 添加 PDF 页面标记
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松地将 PDF 页面标记添加到您的 PDF 文档。
type: docs
weight: 40
url: /zh/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

在本教程中，我们将逐步向您介绍如何使用 Aspose.PDF for .NET 向 PDF 文档添加 PDF 页面戳记。我们将向您展示如何使用提供的 C# 源代码将自定义图章添加到 PDF 文档的特定页面。

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
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 3 步：创建页面缓冲区

现在您已经上传了 PDF 文档，您可以创建要添加的页面戳记。方法如下：

```csharp
//创建页面缓冲区
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

上面的代码使用 PDF 文档的第一页创建了一个新的页面缓冲区。

## 第 4 步：配置页面缓冲区属性

在将页面图章添加到PDF文档之前，您可以配置图章的各种属性，例如背景、位置、旋转等。方法如下：

```csharp
//配置页面缓冲区属性
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

您可以根据需要调整这些属性。

## 第 5 步：将页面戳记添加到 PDF

现在页面戳已准备就绪，您可以将其添加到 PDF 文档的特定页面。就是这样：

```csharp
//将页面缓冲区添加到特定页面
pdfDocument.Pages[1].AddStamp(pageStamp);
```

上面的代码将页面标记添加到 PDF 文档的第一页。如果需要，您可以指定另一个页面。

## 第 6 步：保存输出文档

添加页面戳记后，您可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存输出文件
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 添加 PDFPage Stamp 的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

//创建页戳
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

//在特定页面上添加图章
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

//保存输出文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

上述代码将编辑好的PDF文档保存到指定目录。

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 添加 PDF 页面戳记。现在您可以将这些知识应用到您自己的项目中，以将自定义图章添加到 PDF 文档的特定页面。
