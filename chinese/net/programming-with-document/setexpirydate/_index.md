---
title: 设置到期日
linktitle: 设置到期日
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 在 PDF 文档中设置到期日期。
type: docs
weight: 300
url: /zh/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET 是一个功能强大的库，它提供了处理 PDF 文件的各种功能。其中一项功能是能够为 PDF 文档设置到期日期。在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 为 PDF 文档设置到期日期的过程。 

## 大纲
1. 什么是 Aspose.PDF for .NET？
2. Aspose.PDF for .NET 设置到期日功能
3. 设置环境
4. 创建新的 PDF 文档
5. 向 PDF 文档添加页面
6. 向 PDF 文档添加文本
7. 创建一个 JavaScript 对象来设置 PDF 到期日期
8. 将 JavaScript 设置为 PDF 打开操作
9. 保存 PDF 文档
10. 使用 Aspose.PDF for .NET 设置到期日期的示例源代码
11. 结论
12. 常见问题

## 第一步：设置文档目录路径

在我们开始之前，我们需要将路径设置为我们的 PDF 文档所在的目录。我们将把这个路径存储在一个名为“dataDir”的变量中。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新的 PDF 文档

要创建一个新的 PDF 文档，我们需要实例化一个新的`Aspose.Pdf.Document`目的。我们可以使用以下代码来做到这一点：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 第 3 步：向 PDF 文档添加新页面

一旦我们创建了 PDF 文档，我们就可以向其中添加一个新页面。我们可以使用以下代码来做到这一点：

```csharp
doc.Pages.Add();
```

## 第 4 步：将文本添加到 PDF 文档

将页面添加到 PDF 文档后，我们可以使用`Paragraphs`收藏。我们可以使用以下代码来做到这一点：

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## 第 5 步：使用 JavaScript 设置 PDF 到期日期

要设置 PDF 到期日期，我们需要创建一个 JavaScript 对象。我们可以使用以下代码来做到这一点：

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

//将 JavaScript 设置为 PDF 打开操作
doc.OpenAction = javaScript;
```

在此代码中，我们将到期日期设置为 2017 年 5 月。

## 第 6 步：保存 PDF 文件

设置到期日期后，您需要保存 PDF 文件。为此，您可以使用`Save`的方法`Document`对象并传入要保存更新的 PDF 文件的路径。

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 设置到期日期的示例源代码

下面是使用 Aspose.PDF for .NET 设置到期日期的完整示例源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//实例化文档对象
	Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
	//将页面添加到 PDF 文件的页面集合
	doc.Pages.Add();
	//将文本片段添加到页面对象的段落集合
	doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
	//创建 JavaScript 对象以设置 PDF 到期日期
	JavascriptAction javaScript = new JavascriptAction(
	"var year=2017;"
	+ "var month=5;"
	+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
	+ "expiry = new Date(year, month);"
	+ "if (today.getTime() > expiry.getTime())"
	+ "app.alert('The file is expired. You need a new one.');");
	//将 JavaScript 设置为 PDF 打开操作
	doc.OpenAction = javaScript;

	dataDir = dataDir + "SetExpiryDate_out.pdf";
	//保存 PDF 文档
	doc.Save(dataDir);
	
```
