---
title: 向 PDF 文档添加删除 Javascript
linktitle: 添加删除 Javascript 到文档
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中添加和删除 JavaScript。带有文档级脚本代码教程的分步指南。
type: docs
weight: 30
url: /zh/net/programming-with-document/addremovejavascripttodoc/
---
## 介绍

在本指南中，我们将介绍如何使用 Aspose.PDF for .NET 将 JavaScript 插入 PDF 文件以及如何在必要时将其删除。在本教程结束时，您将清楚地了解如何轻松地在 PDF 中操作 JavaScript。

## 先决条件

在深入研究代码之前，您需要设置一些东西：

1.  Aspose.PDF for .NET：您需要在项目中安装 Aspose.PDF for .NET 库。如果您还没有，请从[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net/).
2. IDE 或文本编辑器：您可以使用任何与 .NET 兼容的 IDE，例如 Visual Studio。
3. 基本 C# 知识：本教程假设您熟悉 C# 并熟悉 PDF 操作。
4. 许可证：请确保应用有效的许可证以避免限制。您可以从[这里](https://purchase.aspose.com/temporary-license/).

## 导入包

要开始使用 Aspose.PDF for .NET，您需要将必要的命名空间导入到您的项目中。操作方法如下：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

这两个命名空间至关重要。`Aspose.Pdf`允许您处理 PDF 文档，同时`System.Collections`将用于处理 JavaScript 键。

让我们将在 PDF 中添加和删除 JavaScript 的整个过程分解为易于遵循的步骤。

## 步骤 1：初始化新的 PDF 文档

您需要做的第一件事是创建一个新的 PDF 文档。此文档将作为我们添加 JavaScript 的空白画布。

```csharp
Document doc = new Document();
doc.Pages.Add();
```

在这里，我们正在初始化一个新的`Document`对象并向其中添加空白页。将其视为 PDF 的基础。

## 步骤 2：将 JavaScript 添加到 PDF

现在我们有了一个文档，是时候向其中添加一些 JavaScript 了。PDF 中的 JavaScript 可用于添加自定义行为，例如警报或表单验证。

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

在此代码片段中，我们添加了两个 JavaScript 函数（`func1`和`func2` ) 到 PDF。这些函数可以执行各种任务，具体取决于您的需求。在这里，我们只是调用一个名为`hello()`.

## 步骤 3：使用 JavaScript 保存 PDF

添加所需的 JavaScript 后，就可以保存 PDF 了。

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

这将使用 JavaScript 将文档保存在以下名称下`AddJavascript.pdf`在指定目录中（`dataDir`）。

## 步骤 4：在现有 PDF 中加载并查看 JavaScript

假设您需要检查或修改现有 PDF 中的 JavaScript 函数。第一步是加载 PDF 文件并访问 JavaScript 键。

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

我们正在加载现有的`AddJavascript.pdf`并将 JavaScript 键存储在列表中。`Keys`属性返回附加到文档的所有 JavaScript 函数的名称。

## 步骤 5：显示 JavaScript 函数

接下来，我们可以遍历 JavaScript 函数来查看文档中可用的内容。

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

这会将每个 JavaScript 函数名称及其对应的代码打印到控制台。如果你想验证文档中当前有哪些函数，这将非常有用。

## 步骤 6：从 PDF 中删除 JavaScript

现在，假设你想删除一个特定的 JavaScript 函数，例如`func1`。具体操作如下：

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

这`Remove`方法将 JavaScript 函数的名称作为参数并将其从文档中删除。

## 步骤 7：验证 JavaScript 删除

删除 JavaScript 后，您可以重新打印剩余的函数以确认`func1`已成功删除。

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

代码的最后一部分确保一切就绪并且 JavaScript 函数得到正确更新。

## 结论

恭喜！您刚刚学会了如何使用 Aspose.PDF for .NET 在 PDF 文档中添加和删除 JavaScript。此强大功能可用于各种任务，从添加动态消息到执行自定义计算或验证。通过在 PDF 中操作 JavaScript，您可以显著增强用户体验。

## 常见问题解答

### 我可以向单个 PDF 添加多个 JavaScript 函数吗？
当然！您可以使用`doc.JavaScript`收藏。

### 如果我尝试删除不存在的 JavaScript 函数会发生什么？
如果该函数不存在，则`Remove`方法不会引发错误，但也不会删除任何东西。

### PDF 打开后是否可以立即运行 JavaScript？
是的！您可以将 JavaScript 配置为在某些触发器上运行，例如打开文档或单击按钮。

### 将 JavaScript 添加到 PDF 后我可以编辑它吗？
是的，您可以加载现有的 PDF，访问其 JavaScript，修改代码，然后再次保存该文档。

### 删除 JavaScript 会影响 PDF 的其余内容吗？
不会，删除 JavaScript 只会影响脚本。PDF 的内容保持不变。