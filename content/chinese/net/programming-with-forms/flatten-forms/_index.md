---
title: 展平 PDF 文档中的表单
linktitle: 展平 PDF 文档中的表单
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松展平 PDF 文档中的表单。
type: docs
weight: 100
url: /zh/net/programming-with-forms/flatten-forms/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 展平表单。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第 1 步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源 PDF 表单

加载源 PDF 表单：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 步骤 3：展平表格

首先检查文档中是否有任何表单字段。如果是这样，请迭代每个字段并应用扁平化：

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## 步骤 4：保存更新后的文档

保存更新的 PDF 文档：

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 拼合表单的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载源 PDF 表单
Document doc = new Document(dataDir + "input.pdf");
//扁平化表格
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
//保存更新后的文档
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 展平表单。通过执行这些步骤，您可以轻松地展平 PDF 文档中的表单、使字段不可编辑以及将注释与文档内容合并。

### 常见问题解答

#### 问：Aspose.PDF for .NET 中的“扁平化表单”是什么意思？

答：Aspose.PDF for .NET 中的扁平化表单是指使 PDF 文档中的表单字段不可编辑并将注释（例如表单字段、注释和数字签名）与文档内容合并的过程。一旦表单被扁平化，用户就无法修改表单字段，并且表单字段的视觉外观成为PDF文档静态内容的一部分。

#### 问：我可以反转拼合过程并使表单字段再次可编辑吗？

答：不可以，一旦表单字段被展平，使用 Aspose.PDF for .NET 的过程就不可逆转。扁平化将表单字段的外观与 PDF 内容永久合并，并且各个表单字段元素不再可访问或可编辑。

#### 问：什么时候应该拼合 PDF 文档中的表单？

答：当您想要保留 PDF 文档中表单字段和注释的视觉外观，同时防止用户修改数据时，扁平化表单非常有用。当您想要共享带有预先填写的表单数据或注释（收件人不应更改）的 PDF 文档时，通常会执行此操作。

#### 问：扁平化表单是否会影响其他注释，例如数字签名？

答：是的，拼合表单会将所有注释（包括数字签名）与 PDF 内容合并。一旦表单被扁平化，任何现有的数字签名将成为文档的永久部分，用户无法修改或删除它们。

#### 问：我可以有选择地展平特定表单字段并保留其他字段可编辑吗？

答：是的，您可以有选择地展平 PDF 文档中的特定表单字段，同时保留其他字段可编辑。您可以选择根据名称或其他条件仅展平所需的表单字段，而不是使用代码展平所有表单字段。