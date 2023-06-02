---
title: 从所有字段中获取值
linktitle: 从所有字段中获取值
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文档中所有表单域的值。
type: docs
weight: 150
url: /zh/net/programming-with-forms/get-values-from-all-fields/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取 PDF 文档中所有表单域的值。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开文档

打开PDF文档：

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## 第 3 步：获取所有字段的值

遍历文档中的所有表单字段并获取它们的名称和值：

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### 使用 Aspose.Words for .NET 从所有字段中获取值的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
//从所有字段中获取值
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文档中所有表单域的值。按照这些步骤，您可以使用 Aspose.PDF 轻松地从您的 PDF 文档中提取所有表单域的值。