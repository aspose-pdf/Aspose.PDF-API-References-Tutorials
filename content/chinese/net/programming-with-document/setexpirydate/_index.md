---
title: 在 PDF 文件中设置到期日期
linktitle: 在 PDF 文件中设置到期日期
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置到期日期。通过本分步指南增强文档安全性。
type: docs
weight: 300
url: /zh/net/programming-with-document/setexpirydate/
---
## 介绍

在当今的数字时代，管理和保护文档比以往任何时候都更加重要。想象一下，发送一份 PDF 文件，该 PDF 文件在某个日期后自动变为不可访问。听起来很神奇，对吧？好吧，使用 Aspose.PDF for .NET，您可以轻松为 PDF 文件设置到期日期。此功能对于需要在一定时间后限制的敏感文档特别有用。在本教程中，我们将逐步引导您完成在 PDF 文件中设置到期日期的过程。所以，戴上你的编码帽，让我们开始吧！

## 先决条件

在开始之前，您需要做好以下几件事：

1. 开发环境：确保您已设置 .NET 开发环境。这可以是 Visual Studio 或任何其他支持 .NET 的 IDE。
2.  Aspose.PDF for .NET：您需要安装 Aspose.PDF 库。如果您尚未安装，可以从以下网址下载[这里](https://releases.aspose.com/pdf/net/).
3. C# 基础知识：本教程假设您对 C# 编程有基本的了解。如果您是 C# 新手，请不要担心！我们会尽量讲得简单明了。

## 导入包

要开始使用 Aspose.PDF，您需要在 C# 项目中导入必要的命名空间。具体操作如下：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

这些命名空间使您能够访问在 Aspose.PDF 中处理 PDF 文档所需的核心功能。

## 步骤 1：设置文档目录

首先，您需要指定文档目录的路径。这是输出 PDF 的保存位置。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存 PDF 文件的实际路径。这就像告诉您的程序，“嘿，这是我保存文件的地方！”

## 步骤 2：实例化文档对象

接下来，您需要创建一个新的实例`Document`类。这是您创建 PDF 的画布。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

想想`Document`对象就像一张白纸。你可以随意添加内容！

## 步骤 3：向 PDF 添加页面

现在您已设置好文档，是时候添加页面了。这是您的内容要放的地方。

```csharp
doc.Pages.Add();
```

您刚刚在 PDF 中创建了一个新页面。这就像在笔记本中添加了一个新页面，您可以在其中记下自己的想法。

## 步骤 4：向页面添加文本

让我们通过添加一些文本使此页面更有趣一些。我们将添加一个简单的“Hello World”消息。

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

这行代码将文本片段添加到 PDF 的第一页。就像在页面顶部写一个标题一样！

## 步骤 5：创建到期日期的 JavaScript

现在到了最有趣的部分！您将创建一个 JavaScript 操作来检查 PDF 的有效期。如果当前日期超过有效期，则会向用户发出一条消息提醒。

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

以下是具体情况：
- 您定义到期年份和月份。
- 您将获得今天的日期。
- 您将今天的日期与到期日期进行比较。
- 如果今天的日期已过有效期，则会弹出一条消息！

## 步骤 6：将 JavaScript 设置为 PDF 打开操作

现在，您需要将 JavaScript 操作设置为 PDF 文档的打开操作。这意味着 JavaScript 将在 PDF 打开后立即运行。

```csharp
doc.OpenAction = javaScript;
```

这行代码告诉 PDF 在有人打开时执行 JavaScript。这就像设置一个提醒，只要你打开日历就会响起！

## 步骤 7：保存 PDF 文档

最后，是时候使用到期日期功能保存您的 PDF 文档了。 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

此行将您的 PDF 保存到指定目录，名称为“SetExpiryDate_out.pdf”。就像将您完成的艺术品放入画框中一样！

## 结论

就这样！您已成功使用 Aspose.PDF for .NET 创建了带有到期日期的 PDF 文件。此功能不仅增强了安全性，还确保敏感信息得到控制。无论您发送的是合同、报告还是任何其他重要文件，设置到期日期都可能改变游戏规则。

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个功能强大的库，允许开发人员在 .NET 应用程序中创建、操作和转换 PDF 文档。

### 我可以免费使用 Aspose.PDF 吗？
是的，您可以使用 Aspose.PDF 的免费试用版。您可以下载它[这里](https://releases.aspose.com/).

### 如何购买 Aspose.PDF？
您可以通过访问购买 Aspose.PDF[购买页面](https://purchase.aspose.com/buy).

### 如果我需要支持怎么办？
如果您有任何疑问或需要帮助，您可以访问[Aspose 支持论坛](https://forum.aspose.com/c/pdf/10).

### 我可以获得 Aspose.PDF 的临时许可证吗？
是的，你可以申请临时执照[这里](https://purchase.aspose.com/temporary-license/).