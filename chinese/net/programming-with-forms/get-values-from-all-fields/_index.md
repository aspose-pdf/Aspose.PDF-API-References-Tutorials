---
title: 从 PDF 文档中的所有字段获取值
linktitle: 从 PDF 文档中的所有字段获取值
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文档中所有表单字段的值。
type: docs
weight: 150
url: /zh/net/programming-with-forms/get-values-from-all-fields/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取 PDF 文档中所有表单字段的值。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第 1 步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：打开文档

打开 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## 步骤 3：获取所有字段的值

循环遍历文档中的所有表单字段并获取它们的名称和值：

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### 使用 Aspose.PDF for .NET 从所有字段获取值的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
//从所有字段获取值
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文档中所有表单字段的值。通过执行这些步骤，您可以使用 Aspose.PDF 轻松地从 PDF 文档中提取所有表单字段的值。

### 常见问题解答

#### 问：我可以在使用 Aspose.PDF for .NET 检索表单字段的值时修改它们吗？

答：是的，您可以在使用 Aspose.PDF for .NET 检索表单字段的同时修改它们的值。一旦你拥有了`Field`代表表单字段的对象，您可以更新其`Value`具有所需价值的财产。进行必要的更改后，您可以保存更新的 PDF 文档以反映更改。

#### 问：如何根据类型（例如文本字段、复选框）过滤和检索特定表单字段？

答：要根据类型检索特定的表单字段，您可以使用条件语句或 LINQ 查询来过滤感兴趣的字段。您可以使用字段的字段检查每个表单字段的类型`FieldType`属性，然后相应地检索值。

#### 问：如果 PDF 文档没有表单字段会怎样？

答：如果 PDF 文档不包含任何表单字段，则`pdfDocument.Form`属性将返回一个空集合。在这种情况下，检索值的循环将不会执行，并且不会显示任何值。

#### 问：我可以按特定顺序提取表单字段值或按字母顺序排序吗？

答：检索表单字段的顺序取决于 PDF 文档的底层结构。 Aspose.PDF for .NET 按照表单字段添加到文档的顺序返回表单字段。如果您想按特定顺序显示或处理表单字段，您可以根据您的要求实现自定义排序逻辑。

#### 问：如何处理带有受密码保护的表单字段的加密 PDF 文档？

答：Aspose.PDF for .NET 提供了处理加密 PDF 文档和受密码保护的表单字段的功能。在加载文档之前，您可以使用以下命令设置密码`pdfDocument.Password`属性来访问受保护的 PDF 文档及其表单字段。