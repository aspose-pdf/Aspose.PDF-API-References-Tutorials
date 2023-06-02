---
title: 删除表单域
linktitle: 删除表单域
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松从您的 PDF 文档中删除不需要的表单域。
type: docs
weight: 50
url: /zh/net/programming-with-forms/delete-form-field/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 删除表单域。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开文档

打开现有的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## 第 3 步：删除特定字段

使用名称删除特定的表单字段：

```csharp
pdfDocument.Form.Delete("textbox1");
```

## 第四步：保存编辑好的文档

保存修改后的 PDF 文档：

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.Words for .NET 删除表单字段的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
//按名称删除特定字段
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
//保存修改后的文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 删除表单域。按照这些步骤，您可以使用 Aspose.PDF 轻松地从 PDF 文档中删除不需要的表单域。