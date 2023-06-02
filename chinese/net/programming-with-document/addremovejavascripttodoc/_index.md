---
title: 添加删除 Javascript 到文档
linktitle: 添加删除 Javascript 到文档
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中添加和删除 JavaScript。带有文档级脚本编写代码教程的分步指南。
type: docs
weight: 30
url: /zh/net/programming-with-document/addremovejavascripttodoc/
---

要在 PDF 文档中添加和删除 JavaScript，我们将使用 Aspose.PDF for .NET 库。这个强大的库允许我们在 .NET 应用程序中操作 PDF 文件。按照下面的分步说明使用 Aspose.PDF for .NET 添加和删除 JavaScript。

## 步骤 1：创建一个新的 PDF 文档

首先创建一个新的实例`Document`Aspose.PDF for .NET 提供的类。这将用作我们将在其中添加 JavaScript 的 PDF 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## 第 2 步：在文档级别添加 JavaScript

要在文档级别添加 JavaScript，请使用`JavaScript`的财产`Document`班级。将 JavaScript 函数分配给 JavaScript 字典中的键。

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

在本教程中，我们添加了两个 JavaScript 函数，`func1`和`func2`, 到 PDF 文档。

## 第 3 步：删除文档级 JavaScript

要在文档级别删除 JavaScript，请加载 PDF 文档并访问`JavaScript`字典。遍历键并删除所需的 JavaScript 函数。

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

在本教程中，我们删除了`func1`PDF 文档中的 JavaScript 函数。

## 第 4 步：保存并验证更改

保存修改后的 PDF 文档并验证更改。

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

此代码将保存修改后的 PDF 文档并显示成功消息。

### 使用 Aspose.PDF for .NET 从 PDF 文档中添加和删除 Javascript 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

//删除文档级 JavaScript
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## 结论

在本文中，我们提供了使用 Aspose.PDF for .NET 在 PDF 文档中添加和删除 JavaScript 的分步指南。按照说明并利用提供的代码教程，您可以轻松地将 JavaScript 合并到您的 PDF 文档中，并在需要时将其删除。 JavaScript 在您的 PDF 文件中启用动态功能和交互性，从而增强用户体验。