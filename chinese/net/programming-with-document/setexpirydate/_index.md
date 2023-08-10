---
title: 在 PDF 文件中设置到期日期
linktitle: 在 PDF 文件中设置到期日期
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置到期日期。
type: docs
weight: 300
url: /zh/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET 是一个功能强大的库，提供了处理 PDF 文件的各种功能。其中一项功能是能够为 PDF 文档设置到期日期。在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 设置 PDF 文档到期日期的过程。 

## 第一步：设置文档目录路径

在开始之前，我们需要设置 PDF 文档所在目录的路径。我们将该路径存储在名为“dataDir”的变量中。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新的 PDF 文档

要创建一个新的 PDF 文档，我们需要实例化一个新的`Aspose.Pdf.Document`目的。我们可以使用以下代码来做到这一点：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 步骤 3：向 PDF 文档添加新页面

创建 PDF 文档后，我们可以向其中添加新页面。我们可以使用以下代码来做到这一点：

```csharp
doc.Pages.Add();
```

## 步骤 4：将文本添加到 PDF 文档

将页面添加到 PDF 文档后，我们可以使用以下命令向其添加文本`Paragraphs`收藏。我们可以使用以下代码来做到这一点：

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

## 步骤 6：保存 PDF 文件

设置到期日期后，您需要保存 PDF 文件。为此，您可以使用`Save`的方法`Document`对象并传入要保存更新的 PDF 文件的路径。

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 设置到期日期的示例源代码

以下是使用 Aspose.PDF for .NET 设置到期日期的完整示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化文档对象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//将页面添加到 PDF 文件的页面集合
doc.Pages.Add();
//将文本片段添加到页面对象的段落集合中
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
//创建 JavaScript 对象来设置 PDF 到期日期
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

## 结论

使用 Aspose.PDF for .NET 设置 PDF 文档的到期日期是一项有用的功能，可确保文档仅在指定期限内有效。通过遵循分步指南并使用提供的 C# 源代码，开发人员可以轻松设置到期日期并创建具有有时效性的 PDF。此功能对于需要在有限时间内访问或分发的文档特别有用。

### 有关在 PDF 文件中设置到期日期的常见问题解答

#### 问：我可以为 PDF 文档设置不同的到期日期吗？

答：是的，您可以通过修改步骤 5 中的 JavaScript 代码来为 PDF 文档设置不同的到期日期。在提供的示例中，到期日期设置为 2017 年 5 月。要设置不同的到期日期，您需要修改`year`和`month`JavaScript 代码中的变量设置为所需的年份和月份。

#### 问：PDF 文档过期后会发生什么情况？

答：当 PDF 文档已过期（如 JavaScript 代码中所指定）时，查看器将显示一条警报消息，指示该文件已过期并且用户需要新的文件。打开 PDF 时将显示此警告消息。

#### 问：我可以使用具体时间而不是仅使用日期作为到期日期吗？

答：是的，您可以在 JavaScript 代码中设置到期日期的具体时间。通过修改`expiry`如果您在 JavaScript 代码中包含所需时间的变量，则可以设置到期日期的特定时间。