---
title: 添加删除 Javascript 到 PDF 文档
linktitle: 添加删除 Javascript 到文档
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中添加和删除 JavaScript。包含文档级脚本编写代码教程的分步指南。
type: docs
weight: 30
url: /zh/net/programming-with-document/addremovejavascripttodoc/
---
要向 PDF 文档添加和删除 JavaScript，我们将利用 Aspose.PDF for .NET 库。这个强大的库允许我们在.NET应用程序中操作PDF文件。请按照以下分步说明使用 Aspose.PDF for .NET 添加和删除 JavaScript。

## 第 1 步：创建新的 PDF 文档

首先创建一个新实例`Document` Aspose.PDF for .NET 提供的类。这将作为 PDF 文档，我们将在其中添加 JavaScript。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## 步骤 2：在文档级别添加 JavaScript

要在文档级别添加 JavaScript，请使用`JavaScript`的财产`Document`班级。将 JavaScript 函数分配给 JavaScript 字典中的键。

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

在本教程中，我们添加了两个 JavaScript 函数，`func1`和`func2`，到 PDF 文档。

## 第 3 步：删除文档级 JavaScript

要在文档级别删除 JavaScript，请加载 PDF 文档并访问`JavaScript`字典。迭代这些键并删除所需的 JavaScript 函数。

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

在本教程中，我们删除`func1`PDF 文档中的 JavaScript 函数。

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

在本文中，我们提供了使用 Aspose.PDF for .NET 在 PDF 文档中添加和删除 JavaScript 的分步指南。通过遵循说明并利用提供的代码教程，您可以轻松地将 JavaScript 合并到 PDF 文档中，并在需要时将其删除。 JavaScript 可在 PDF 文件中实现动态功能和交互性，从而增强用户体验。


### 添加删除 JavaScript 到 PDF 文档的常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个功能强大的库，允许开发人员在.NET 应用程序中有效地操作 PDF 文件。它提供了以编程方式处理 PDF 文档的广泛功能。

#### 问：如何使用 Aspose.PDF for .NET 将 JavaScript 添加到 PDF 文档？

答：您可以使用以下命令在文档级别添加 JavaScript`JavaScript`的财产`Document`班级。只需将 JavaScript 函数分配给 JavaScript 字典中的键即可。

#### 问：我可以使用 Aspose.PDF for .NET 从 PDF 文档中删除 JavaScript 吗？

答：是的，您可以通过访问从 PDF 文档中删除 JavaScript`JavaScript`字典并删除所需的 JavaScript 函数。

#### 问：Aspose.PDF for .NET 适合专业项目吗？

答：当然，Aspose.PDF for .NET 广泛应用于 PDF 操作和生成任务的专业项目中。它提供高性能和可靠的功能。

#### 问：将 JavaScript 添加到 PDF 文档有什么好处？

答：将 JavaScript 添加到 PDF 文档使您能够创建交互式动态 PDF 文件。您可以实现表单验证、执行计算并添加各种交互功能来增强用户体验。