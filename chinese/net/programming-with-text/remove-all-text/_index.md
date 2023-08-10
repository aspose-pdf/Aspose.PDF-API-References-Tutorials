---
title: 删除所有文本
linktitle: 删除所有文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文档中删除所有文本。
type: docs
weight: 280
url: /zh/net/programming-with-text/remove-all-text/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除所有文本。我们将逐步完成打开 PDF、从每个页面选择和删除文本以及使用提供的 C# 源代码保存修改后的 PDF 的过程。

## 要求

在开始之前，请确保您具备以下条件：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本了解。

## 第 1 步：设置文档目录

首先，您需要设置 PDF 文件所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含 PDF 文件的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

接下来，我们使用以下命令打开 PDF 文档`Document`来自 Aspose.PDF 库的类。

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## 第 3 步：删除每页中的文本

我们循环遍历 PDF 文档的所有页面并使用`OperatorSelector`选择每页上的所有文本。然后，我们删除选定的文本。

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## 第4步：保存修改后的PDF

最后，我们将修改后的PDF文档保存到指定的输出文件中。

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### 使用 Aspose.PDF for .NET 删除所有文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
//循环浏览 PDF 文档的所有页面
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	//选择页面上的所有文本
	page.Contents.Accept(operatorSelector);
	//删除所有文字
	page.Contents.Delete(operatorSelector.Selected);
}
//保存文档
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除所有文本。通过遵循分步指南并执行提供的 C# 代码，您可以打开 PDF，选择并删除每个页面中的文本，然后保存修改后的 PDF。