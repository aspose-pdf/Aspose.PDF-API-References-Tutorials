---
title: 按 Tab 键顺序检索表单字段
linktitle: 按 Tab 键顺序检索表单字段
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 按 Tab 键顺序检索表单字段。
type: docs
weight: 240
url: /zh/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
当使用 Aspose.PDF for .NET 在 C# 中处理 PDF 文档时，您可能会遇到需要按特定 Tab 键顺序检索表单字段的情况。当您想要根据表单字段的选项卡顺序对表单字段执行操作时，这会很有用。在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 按 Tab 键顺序检索表单字段。

## 要求

在我们开始之前，请确保您具备以下先决条件：

- 您的系统上安装了 Visual Studio
- 安装了 Aspose.PDF for .NET 库

现在，让我们深入了解按 Tab 键顺序检索表单字段的步骤。

## 第1步：设置文档目录

首先，您需要设置 PDF 文档所在的文档目录。您可以通过指定目录的路径来完成此操作`dataDir`多变的。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第2步：加载PDF文档

在此步骤中，我们将使用 Aspose.PDF for .NET 加载 PDF 文档。这`Document`类提供加载和操作 PDF 文档的能力。

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

这里，`"Test2.pdf"`是您要加载的 PDF 文档的名称。确保该文档存在于指定的文档目录中。

## 步骤 3：按 Tab 键顺序检索表单字段

要按 Tab 键顺序检索表单字段，我们需要访问`FieldsInTabOrder`的财产`Page`班级。此属性返回按选项卡顺序排序的表单字段列表。

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

在上面的代码片段中，我们从第二页（`doc.Pages[1]` ）并迭代每个字段以将其部分名称连接到`s`多变的。您可以根据您的具体要求修改此代码片段。

## 第 4 步：修改 Tab 键顺序

如果您想修改表单字段的 Tab 键顺序，可以通过访问`TabOrder`每个字段的属性并分配新的 Tab 键顺序值。这是一个例子：

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

在上面的代码片段中，我们将新的 Tab 键顺序值分配给三个表单字段（`doc.Form[3]`, `doc.Form[1]` ， 和`doc.Form[2]`）。根据您的具体要求调整字段索引和 Tab 键顺序值。

## 第五步：保存修改后的文档

修改表单字段的 Tab 键顺序后，您需要保存修改后的文档。您可以使用`Save`的方法`Document`班级。

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

这里，`"39522_out.pdf"`是将保存修改后的文档的输出文件的名称。指定输出文件所需的名称和位置。

### 使用 Aspose.PDF for .NET 按 Tab 键顺序检索表单字段的示例源代码 
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

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 按 Tab 键顺序检索表单字段。我们介绍了加载 PDF 文档、按 Tab 键顺序检索表单字段、修改 Tab 键顺序以及保存修改后的文档所涉及的步骤。通过执行这些步骤，您可以有效地使用表单字段并根据您的要求自定义其选项卡顺序。


### 常见问题解答

#### 问：如何在 C# 代码中使用检索到的表单字段进行进一步处理？

答：您可以通过访问 C# 代码中检索到的表单字段的属性来使用它们，例如`Value`, `Name`, `Rect`等。这些属性允许您根据需要读取和修改表单字段数据。

#### 问：我可以按 Tab 键顺序从 PDF 文档的所有页面检索表单字段吗？

答：是的，您可以通过迭代每个页面并访问 PDF 文档的所有页面来检索表单字段。`FieldsInTabOrder`属性如教程中所示。这将为您提供按所有页面的选项卡顺序排序的表单字段。

#### 问：是否可以按 Tab 键顺序仅检索特定类型的表单字段，例如文本字段或复选框？

答：是的，您可以在按 Tab 键顺序检索表单字段后，根据其类型（例如文本字段或复选框）过滤表单字段。您可以使用条件语句来检查每个表单字段的类型并进行相应的处理。

#### 问：我可以根据表单字段的名称而不是 Tab 键顺序来检索表单字段吗？

答：是的，您可以使用以下命令根据名称检索表单字段`doc.Form`集合并指定字段名称作为索引。例如，`doc.Form["fieldName"]`将检索具有指定名称的表单字段。

#### 问：Aspose.PDF for .NET 支持处理加密的 PDF 文档吗？

答：是的，Aspose.PDF for .NET 提供对加密 PDF 文档的支持。您可以使用适当的密码参数加载和操作加密的 PDF 文件。