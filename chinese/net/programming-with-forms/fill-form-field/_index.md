---
title: 填写表单域
linktitle: 填写表单域
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松填写 PDF 文档中的表单域。
type: docs
weight: 80
url: /zh/net/programming-with-forms/fill-form-field/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 填充表单域。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开文档

打开现有的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## 第 3 步：获取字段

获取所需的表单字段（在本例中，我们使用“textbox1”字段）：

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 第 4 步：更改字段值

使用所需的值修改字段值：

```csharp
textBoxField.Value = "Value to fill in the field";
```

## 第 5 步：保存更新后的文档

保存更新后的 PDF 文档：

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.Words for .NET 填写表单字段的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
//获取字段
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
//修改字段值
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 填充表单字段。按照这些步骤，您可以使用 Aspose.PDF 轻松更改 PDF 文档中的表单域值。