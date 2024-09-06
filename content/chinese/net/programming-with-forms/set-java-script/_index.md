---
title: 设置 Java 脚本
linktitle: 设置 Java 脚本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的表单字段中设置 JavaScript。
type: docs
weight: 270
url: /zh/net/programming-with-forms/set-java-script/
---
在本指南中，我们将逐步解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文档的表单字段中定义 JavaScript。我们将向您展示如何配置 JavaScript 操作以对文本字段执行特定操作。

## 先决条件

开始之前，请确保您已准备好以下物品：

- 您的系统上安装了 .NET 开发环境。
- 适用于 .NET 的 Aspose.PDF 库。您可以从 Aspose 官方网站下载。

## 步骤 1：配置文档目录

第一步是配置要处理的 PDF 文件所在的文档目录。您可以使用`dataDir`变量来指定目录路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的文档目录的实际路径。

## 步骤 2：加载输入 PDF 文件

在此步骤中，我们将使用`Document`Aspose.PDF 类。

```csharp
//加载输入 PDF 文件
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

确保输入的 PDF 文件存在于指定的文档目录中。

## 步骤 3：访问 TextBox 字段

要将 JavaScript 应用于特定文本字段，我们首先需要访问该字段。在此示例中，我们假设文本字段名为“textbox1”。使用`doc.Form["textbox1"]`方法获取相应的`TextBoxField`目的。

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

确保输入的 PDF 文件中存在指定的文本字段。

## 步骤 4：配置 JavaScript 操作

现在我们已经访问了文本字段，我们可以配置与该字段关联的 JavaScript 操作。在此示例中，我们将使用两个操作：`OnModifyCharacter`和`OnFormat` . 这些操作将使用`JavascriptAction`对象。

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

请务必根据您的需要定制 JavaScript 操作。

## 步骤 5：设置初始字段值

在保存生成的 PDF 之前，我们可以为文本字段设置初始值。在此示例中，我们将为该字段设置值“123”。

```csharp
field.Value = "123";
```

根据您的需要自定义该值。

## 步骤 6：保存生成的 PDF

现在我们已经设置好了文本字段和 JavaScript 操作，我们可以使用`Save`方法`Document`班级。

```csharp
dataDir = dataDir + "Restricted_out.pdf";
//保存生成的 PDF
doc.Save(dataDir);
```

请确保指定生成的 PDF 的完整路径和文件名。


### 使用 Aspose.PDF for .NET 设置 Java 脚本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载输入 PDF 文件
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
//小数点后 2 位数字
//无分隔符
//Neg 风格 = 减号
//没有货币
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
//设置初始字段值
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
//保存结果 PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## 结论

在本指南中，我们学习了如何使用 .NET 版 Aspose.PDF 库在 PDF 文档的表单字段中设置 JavaScript。按照概述的步骤，您可以自定义 JavaScript 操作以对文本字段执行各种操作。请随意进一步探索 .NET 版 Aspose.PDF 的功能，以扩展操作 PDF 文件的可能性。


### 常见问题解答

#### 问：我可以使用 Aspose.PDF for .NET 将 JavaScript 添加到其他表单元素（例如复选框和单选按钮）吗？

答：是的，Aspose.PDF for .NET 允许您将 JavaScript 添加到各种表单元素，包括复选框、单选按钮和下拉列表。您可以使用`JavascriptAction`类来定义不同表单元素的 JavaScript 动作。

#### 问：是否可以使用表单字段中的 JavaScript 验证用户输入？

答：是的，您可以使用 JavaScript 来验证表单字段中的用户输入。通过定义 JavaScript 操作，例如`OnBlur`或者`OnKeystroke`对于表单字段，您可以验证输入的数据并在必要时显示错误消息。

#### 问：我可以使用 Aspose.PDF for .NET 执行复杂的 JavaScript 函数吗？

答：是的，您可以使用 Aspose.PDF for .NET 执行复杂的 JavaScript 函数。您可以灵活地定义自定义 JavaScript 函数并在`JavascriptAction`.

#### 问：除了本教程中提到的事件外，Aspose.PDF for .NET 是否支持其他 JavaScript 事件？

答：是的，Aspose.PDF for .NET 支持各种 JavaScript 事件，包括`OnMouseEnter`, `OnMouseExit`, `OnMouseDown`， 和`OnMouseUp`等等。您可以使用这些事件根据用户交互来触发 JavaScript 操作。

#### 问：我可以使用 Aspose.PDF for .NET 从现有 PDF 文档中提取 JavaScript 代码吗？

答：Aspose.PDF for .NET 提供了从现有 PDF 文档中提取 JavaScript 代码的功能。您可以使用`JavascriptAction`类和其他相关方法来访问和分析PDF表单中的JavaScript操作。