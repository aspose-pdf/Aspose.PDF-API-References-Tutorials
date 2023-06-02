---
title: 设置 Java 脚本
linktitle: 设置 Java 脚本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的表单域中设置 JavaScript。
type: docs
weight: 270
url: /zh/net/programming-with-forms/set-java-script/
---

在本指南中，我们将逐步解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文档的表单域中定义 JavaScript。我们将向您展示如何配置 JavaScript 操作以在文本字段上执行特定操作。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装在系统上的 .NET 开发环境。
- .NET 的 Aspose.PDF 库。可以从Aspose官网下载。

## 第一步：配置文档目录

第一步是配置要处理的 PDF 文件所在的文档目录。您可以使用`dataDir`变量指定目录路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用文档目录的实际路径。

## 第 2 步：加载输入的 PDF 文件

在此步骤中，我们将使用`Document`Aspose.PDF 类。

```csharp
//加载输入 PDF 文件
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

确保输入的 PDF 文件存在于指定的文档目录中。

## 第 3 步：访问 TextBox 字段

要将 JavaScript 应用于特定的文本字段，我们首先需要访问该字段。在此示例中，我们假设文本字段称为“textbox1”。使用`doc.Form["textbox1"]`获取对应的方法`TextBoxField`目的。

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

确保输入的 PDF 文件中存在指定的文本字段。

## 第 4 步：配置 JavaScript 操作

现在我们已经访问了文本字段，我们可以配置与该字段关联的 JavaScript 操作。在这个例子中，我们将使用两个动作：`OnModifyCharacter`和`OnFormat` .这些动作将使用`JavascriptAction`对象。

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

请务必根据您的需要自定义 JavaScript 操作。

## 第 5 步：设置初始字段值

在保存生成的 PDF 之前，我们可以为文本字段设置一个初始值。在此示例中，我们将为该字段设置值“123”。

```csharp
field.Value = "123";
```

根据您的需要自定义此值。

## 第 6 步：保存生成的 PDF

现在我们已经完成了文本字段和 JavaScript 操作的设置，我们可以使用`Save`的方法`Document`班级。

```csharp
dataDir = dataDir + "Restricted_out.pdf";
//保存生成的 PDF
doc.Save(dataDir);
```

请务必指定生成的 PDF 的完整路径和文件名。


### 使用 Aspose.Words for .NET 设置 Java 脚本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载输入 PDF 文件
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
//点后 2 位数
//无分隔符
//否定风格 = 负号
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

在本指南中，我们学习了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档的表单域中设置 JavaScript。按照概述的步骤，您可以自定义 JavaScript 操作以对文本字段执行各种操作。欢迎进一步探索 Aspose.PDF for .NET 的功能，以扩展操作 PDF 文件的可能性。