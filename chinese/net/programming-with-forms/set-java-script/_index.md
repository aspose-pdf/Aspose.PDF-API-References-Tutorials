---
title: 设置Java脚本
linktitle: 设置Java脚本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的表单字段中设置 JavaScript。
type: docs
weight: 270
url: /zh/net/programming-with-forms/set-java-script/
---
在本指南中，我们将逐步解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文档的表单字段中定义 JavaScript。我们将向您展示如何配置 JavaScript 操作以在文本字段上执行特定操作。

## 先决条件

在开始之前，请确保您具备以下条件：

- 您的系统上安装了 .NET 开发环境。
- 适用于 .NET 的 Aspose.PDF 库。您可以从Aspose官方网站下载。

## 第1步：配置文档目录

第一步是配置您要处理的 PDF 文件所在的文档目录。您可以使用`dataDir`变量来指定目录路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

一定要更换`"YOUR DOCUMENTS DIRECTORY"`与文档目录的实际路径。

## 第 2 步：加载输入 PDF 文件

在此步骤中，我们将使用以下命令加载输入 PDF 文件`Document`Aspose.PDF 类。

```csharp
//加载输入 PDF 文件
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

确保输入的 PDF 文件存在于指定的文档目录中。

## 第 3 步：访问文本框字段

要将 JavaScript 应用于特定文本字段，我们首先需要访问该字段。在此示例中，我们假设文本字段称为“textbox1”。使用`doc.Form["textbox1"]`方法获取对应的`TextBoxField`目的。

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

确保输入 PDF 文件中存在指定的文本字段。

## 第 4 步：配置 JavaScript 操作

现在我们已经访问了文本字段，我们可以配置与该字段关联的 JavaScript 操作。在此示例中，我们将使用两个操作：`OnModifyCharacter`和`OnFormat` 。这些操作将使用定义`JavascriptAction`对象。

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

请务必根据您的需要自定义 JavaScript 操作。

## 步骤5：设置初始字段值

在保存生成的 PDF 之前，我们可以为文本字段设置初始值。在此示例中，我们将为该字段设置值“123”。

```csharp
field.Value = "123";
```

根据您的需要自定义该值。

## 第 6 步：保存生成的 PDF

现在我们已经完成了文本字段和 JavaScript 操作的设置，我们可以使用以下命令保存生成的 PDF：`Save`的方法`Document`班级。

```csharp
dataDir = dataDir + "Restricted_out.pdf";
//保存生成的 PDF
doc.Save(dataDir);
```

请务必指定生成的 PDF 的完整路径和文件名。


### 使用 Aspose.PDF for .NET 设置 Java 脚本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载输入 PDF 文件
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
//点后2位数字
//无分隔符
//负风格 = 减号
//没有货币
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
//设置初始字段值
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
//保存生成的 PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## 结论

在本指南中，我们学习了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档的表单字段中设置 JavaScript。通过执行概述的步骤，您可以自定义 JavaScript 操作以在文本字段上执行各种操作。请随意进一步探索 Aspose.PDF for .NET 的功能，以扩展处理 PDF 文件的可能性。


### 常见问题解答

#### 问：我可以使用 Aspose.PDF for .NET 将 JavaScript 添加到其他表单元素（例如复选框和单选按钮）吗？

答：是的，Aspose.PDF for .NET 允许您将 JavaScript 添加到各种表单元素，包括复选框、单选按钮和下拉列表。您可以使用`JavascriptAction`类来定义不同表单元素的 JavaScript 操作。

#### 问：是否可以在表单字段中使用 JavaScript 验证用户输入？

答：是的，您可以使用 JavaScript 来验证表单字段中的用户输入。通过定义 JavaScript 操作，例如`OnBlur`或者`OnKeystroke`对于表单字段，您可以验证输入的数据并在必要时显示错误消息。

#### 问：我可以使用 Aspose.PDF for .NET 执行复杂的 JavaScript 函数吗？

答：是的，您可以使用 Aspose.PDF for .NET 执行复杂的 JavaScript 函数。您可以灵活地定义自定义 JavaScript 函数并在`JavascriptAction`.

#### 问：Aspose.PDF for .NET 是否支持本教程中提到的 JavaScript 事件？

答：是的，Aspose.PDF for .NET 支持广泛的 JavaScript 事件，包括`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` ， 和`OnMouseUp`等。您可以使用这些事件根据用户交互触发 JavaScript 操作。

#### 问：我可以使用 Aspose.PDF for .NET 从现有 PDF 文档中提取 JavaScript 代码吗？

答：Aspose.PDF for .NET 提供了从现有 PDF 文档中提取 JavaScript 代码的功能。您可以使用`JavascriptAction`类和其他相关方法来访问和分析 PDF 表单中的 JavaScript 操作。