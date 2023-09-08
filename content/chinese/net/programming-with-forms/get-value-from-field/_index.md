---
title: 从 PDF 文档中的字段获取值
linktitle: 从 PDF 文档中的字段获取值
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文档中表单字段的值。
type: docs
weight: 140
url: /zh/net/programming-with-forms/get-value-from-field/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取表单字段的值。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第 1 步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：打开文档

打开 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## 第 3 步：获取字段

获取所需的表单字段（在本示例中，我们使用“textbox1”字段）：

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 第四步：获取字段值

使用以下命令获取字段值`Value`财产：

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### 使用 Aspose.PDF for .NET 从字段获取值的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
//获取一个字段
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
//获取字段值
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取表单字段的值。通过执行以下步骤，您可以使用 Aspose.PDF 轻松提取 PDF 文档中特定表单字段的值。

### 常见问题解答

#### 问：我可以在不事先知道表单字段名称的情况下获取表单字段的值吗？

答：不可以，您需要知道表单字段的名称或部分名称才能使用 Aspose.PDF for .NET 获取其值。这`pdfDocument.Form["fieldname"]`语法需要表单字段的确切名称或部分名称才能访问其属性（包括值）。

#### 问：如果PDF文档中不存在表单字段怎么办？

 A：如果PDF文档中不存在表单域，则`pdfDocument.Form["fieldname"]`语法将返回`null`。通过检查来处理此类情况非常重要`null`在访问表单字段的属性之前以避免异常。

#### 问：如何处理不同类型的表单字段（例如复选框、单选按钮）以获取它们的值？

答：要处理不同类型的表单字段，您可以使用 Aspose.PDF for .NET 中提供的适当字段类。例如，使用`CheckBoxField`使用复选框和`RadioButtonField`使用单选按钮。一旦获得正确的字段对象，您就可以访问其属性，包括值。

#### 问：我可以一次获取多个表单字段的值吗？

答：是的，您可以通过使用循环或 LINQ 查询迭代表单字段集合来一次获取多个表单字段的值。这样，您就可以通过编程方式访问 PDF 文档中每个表单字段的值。

#### 问：是否可以修改表单字段的值并将更改保存回 PDF 文档？

答：是的，您可以使用 Aspose.PDF for .NET 修改表单字段的值，并将更改保存回 PDF 文档。更新后`Value`表单字段的属性，您可以使用`pdfDocument.Save()`方法将更改保存到原始 PDF 文档。