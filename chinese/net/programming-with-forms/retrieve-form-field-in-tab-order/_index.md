---
title: 按 Tab 键顺序检索表单域
linktitle: 按 Tab 键顺序检索表单域
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 按 Tab 键顺序检索表单字段。
type: docs
weight: 240
url: /zh/net/programming-with-forms/retrieve-form-field-in-tab-order/
---

当使用 Aspose.PDF for .NET 在 C# 中处理 PDF 文档时，您可能会遇到需要以特定 Tab 键顺序检索表单字段的情况。当您想要根据 Tab 键顺序对表单域执行操作时，这会很有用。在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 按 Tab 键顺序检索表单字段。

## 要求

在我们开始之前，请确保您具备以下先决条件：

- 系统上安装的 Visual Studio
- 已安装 Aspose.PDF for .NET 库

现在，让我们深入了解按 Tab 键顺序检索表单字段的步骤。

## 第 1 步：设置文档目录

首先，您需要设置 PDF 文档所在的文档目录。您可以通过指定目录的路径来执行此操作`dataDir`多变的。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

## 第 2 步：加载 PDF 文档

在此步骤中，我们将使用 Aspose.PDF for .NET 加载 PDF 文档。这`Document`类提供加载和操作 PDF 文档的能力。

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

这里，`"Test2.pdf"`是您要加载的 PDF 文档的名称。确保文档存在于指定的文档目录中。

## 第 3 步：按 Tab 键顺序检索表单字段

要按 Tab 键顺序检索表单字段，我们需要访问`FieldsInTabOrder`的财产`Page`班级。此属性返回按 Tab 键顺序排序的表单域列表。

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

在上面的代码片段中，我们从第二页（`doc.Pages[1]` ) 并遍历每个字段以将它们的部分名称连接到`s`多变的。您可以根据您的具体要求修改此代码段。

## 第 4 步：修改 Tab 键顺序

如果你想修改表单域的跳位顺序，你可以通过访问`TabOrder`每个字段的属性并分配新的 Tab 键顺序值。这是一个例子：

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

在上面的代码片段中，我们将新的 Tab 键顺序值分配给三个表单字段（`doc.Form[3]`, `doc.Form[1]` ， 和`doc.Form[2]`).根据您的特定要求调整字段索引和 Tab 键顺序值。

## 第 5 步：保存修改后的文档

修改表单域的Tab键顺序后，需要保存修改后的文档。您可以使用`Save`的方法`Document`班级。

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

这里，`"39522_out.pdf"`是将保存修改文档的输出文件的名称。为输出文件指定所需的名称和位置。

### 使用 Aspose.Words for .NET 以 Tab 顺序检索表单字段的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 按 Tab 键顺序检索表单字段。我们介绍了加载 PDF 文档、按 Tab 键顺序检索表单域、修改 Tab 键顺序以及保存修改后的文档所涉及的步骤。通过执行这些步骤，您可以有效地使用表单域并根据您的要求自定义它们的 Tab 键顺序。