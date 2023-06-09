---
title: 从 PDF 中删除所有文本
linktitle: 从 PDF 中删除所有文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文档中删除所有文本。
type: docs
weight: 290
url: /zh/net/programming-with-text/remove-all-text-from-pdf/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除所有文本。我们将逐步完成打开 PDF 的过程，使用`TextFragmentAbsorber`删除所有文本，并使用提供的 C# 源代码保存修改后的 PDF。

## 要求

在开始之前，请确保您具有以下内容：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本的了解。

## 第 1 步：设置文档目录

首先，您需要设置 PDF 文件所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`带有 PDF 文件路径的变量。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

接下来，我们使用`Document` Aspose.PDF 库中的类。

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## 第 3 步：删除所有文本

我们初始化一个`TextFragmentAbsorber`对象并使用它从 PDF 文档中删除所有吸收的文本。

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## 第 4 步：保存修改后的 PDF

最后，我们将修改后的PDF文档保存到指定的输出文件中。

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### 使用 Aspose.PDF for .NET 从 PDF 中删除所有文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
//启动 TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
//删除所有吸收的文本
absorber.RemoveAllText(pdfDocument);
//保存文件
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除所有文本。按照分步指南并执行提供的 C# 代码，您可以打开 PDF，使用`TextFragmentAbsorber`并保存修改后的 PDF。