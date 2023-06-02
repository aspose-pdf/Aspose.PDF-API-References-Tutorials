---
title: 从现场获取价值
linktitle: 从现场获取价值
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文档中表单字段的值。
type: docs
weight: 140
url: /zh/net/programming-with-forms/get-value-from-field/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取表单字段的值。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开文档

打开PDF文档：

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## 第 3 步：获取字段

获取所需的表单字段（在本例中，我们使用“textbox1”字段）：

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 第四步：获取字段值

使用获取字段值`Value`财产：

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### 使用 Aspose.Words for .NET 从字段中获取值的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
//获取字段
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
//获取字段值
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取表单字段的值。通过执行这些步骤，您可以使用 Aspose.PDF 轻松提取 PDF 文档中特定表单域的值。