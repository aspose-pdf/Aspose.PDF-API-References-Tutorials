---
title: 展平表格
linktitle: 展平表格
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松展平 PDF 文档中的表单。
type: docs
weight: 100
url: /zh/net/programming-with-forms/flatten-forms/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 扁平化表单。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源 PDF 表单

加载源 PDF 表单：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第 3 步：展平表格

首先检查文档中是否有任何表单域。如果是这样，遍历每个字段并应用展平：

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## 第 4 步：保存更新后的文档

保存更新后的 PDF 文档：

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的 Flatten Forms 示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载源 PDF 表单
Document doc = new Document(dataDir + "input.pdf");
//展平表格
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
//保存更新的文档
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 扁平化表单。通过执行这些步骤，您可以轻松地展平 PDF 文档中的表单，使字段不可编辑并将注释与文档内容合并。