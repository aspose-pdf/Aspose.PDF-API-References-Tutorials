---
title: 将 Java 脚本添加到 PDF 文件
linktitle: 添加 Java 脚本 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将 JavaScript 添加到 PDF 文件。带有文档和页面级脚本代码教程的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document/addjavascripttopage/
---
## 介绍

您是否曾想过如何使用诸如弹出警报或自动打印功能之类的交互式元素来增强 PDF？好消息是，您可以！通过使用 Aspose.PDF for .NET，您可以无缝地将 JavaScript 添加到 PDF 文档中。无论您是自动执行任务还是创建动态用户体验，在 PDF 中嵌入 JavaScript 都会为您的文件提供额外的功能。

## 先决条件

在我们进入编码部分之前，您需要设置一些东西：

-  Aspose.PDF for .NET：从以下网址下载该库[Aspose 版本](https://releases.aspose.com/pdf/net/)或者得到[免费试用](https://releases.aspose.com/).
- 开发环境：任何与 .NET 兼容的 IDE，如 Visual Studio。
- 基本 C# 知识：本指南假设您熟悉基本 C# 语法。
- 临时执照（可选）：您可以获得[临时执照](https://purchase.aspose.com/temporary-license/)如果您想避免开发过程中的限制。

## 导入包

在开始编写代码之前，您需要从 Aspose.PDF 库导入必要的命名空间。这些命名空间将允许您轻松操作 PDF 并添加 JavaScript 操作。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

现在您已经导入了正确的命名空间，可以开始编码了。

## 步骤 1：加载现有 PDF

首先，您需要加载要添加 JavaScript 的 PDF 文档。此步骤为所有进一步的修改奠定了基础。假设您有一个 PDF，想要为其添加动态功能，例如打开时自动打印文档。

加载该 PDF 文件的方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

在此代码片段中，我们使用`Document`类来从指定目录加载现有 PDF 文件。确保替换`"YOUR DOCUMENT DIRECTORY"`使用您的 PDF 文件的实际路径。

## 第 2 步：在文档级别添加 JavaScript

现在，让我们添加一些在文档打开时触发的 JavaScript。在此示例中，我们将编写一个脚本，在用户打开 PDF 时立即打开打印对话框。

文档级 JavaScript 非常适合您想要应用于整个 PDF 的操作。可以将其视为为您的文档设置全局规则。

代码如下：

```csharp
//在文档级别添加 JavaScript
//使用所需的 JavaScript 语句实例化 JavascriptAction
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

//将 JavascriptAction 对象分配给 Document 的 OpenAction
doc.OpenAction = javaScript;
```

在此步骤中，我们创建一个`JavascriptAction`定义 JavaScript 函数的对象，用于在打开文档时打开打印对话框。`doc.OpenAction`然后将属性分配给此 JavaScript 操作。

## 步骤 3：在页面级别添加 JavaScript

并非每个操作都需要影响整个文档。有时，您希望在打开或关闭某些页面时发生特定操作。在这里，我们将为打开和关闭特定页面（假设第 2 页）时设置 JavaScript 操作。

页面级 JavaScript 对于有针对性的交互非常有用。它可以是任何东西，从用户导航到页面时显示消息，到自动填充表单字段等自定义操作。

操作方法如下：

```csharp
//在页面级别添加 JavaScript
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

在此代码片段中，我们添加了两个 JavaScript 操作：
1. OnOpen 操作：当用户打开第 2 页时显示一条警告“第 2 页已打开”。
2. OnClose 操作：当用户离开第 2 页时显示一条警告，提示“第 2 页已关闭”。

这为您的 PDF 增加了一层交互性。想象一下，引导用户完成不同页面上的一系列步骤，并在用户进入或离开页面时弹出警报。

## 步骤 4：保存 PDF 文档

现在，您已将 JavaScript 添加到文档和特定页面。最后一步是将修改后的 PDF 保存到您想要的位置。这部分很简单但至关重要——不要忘记保存您的工作！

代码如下：

```csharp
//指定输出文件路径
dataDir = dataDir + "JavaScript-Added_out.pdf";

//保存更新的 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

在此代码片段中，我们将更新后的文档和添加的 JavaScript 保存到名为`"JavaScript-Added_out.pdf"`。这可确保您不会覆盖原始文件，并为您提供可用的备份。

## 结论

使用 Aspose.PDF for .NET 将 JavaScript 添加到 PDF 文件是创建交互式动态 PDF 的有效方法。无论您是自动执行打印等任务还是创建自定义警报，将 JavaScript 嵌入 PDF 的能力都会让您的文档更具吸引力和功能性。

## 常见问题解答

### 我可以向 PDF 中的不同页面添加多个 JavaScript 操作吗？
是的，您可以为单个页面或整个文档分配不同的 JavaScript 操作。

### 添加 JavaScript 后是否可以从 PDF 中删除？
是的，您可以通过清除`Actions`文档或页面的属性。

### 我可以在 PDF 中使用哪种 JavaScript 函数？
您可以使用 Adobe Acrobat 的 JavaScript 引擎支持的任何 JavaScript，例如打印、警报和表单操作。

### JavaScript 可以在所有 PDF 查看器中运行吗？
大多数 JavaScript 操作都可以在支持交互式 PDF 的 PDF 查看器（如 Adobe Acrobat）中使用。但是，一些基本的 PDF 阅读器可能不支持 JavaScript。

### 我可以根据 PDF 中的用户输入触发 JavaScript 操作吗？
是的，您可以将 JavaScript 绑定到表单字段，以根据用户输入触发操作。