---
title: 使用 DOM 添加 HTML
linktitle: 使用 DOM 添加 HTML
second_title: Aspose.PDF for .NET API 参考
description: 了解如何在 Aspose.PDF for .NET 中使用 DOM 添加 HTML 内容。
type: docs
weight: 40
url: /zh/net/programming-with-text/add-html-using-dom/
---

本教程将指导您完成在 Aspose.PDF for .NET 中使用 DOM（文档对象模型）添加 HTML 内容的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具有以下内容：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- .NET 库的 Aspose.PDF。您可以从 Aspose 官方网站下载它，或者使用像 NuGet 这样的包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入所需的命名空间
在要添加 HTML 内容的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
```

## 第三步：设置文档目录和输出文件路径
在代码中，找到显示的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并更换`"YOUR DOCUMENT DIRECTORY"`与存储文档的目录的路径。

## 第 4 步：创建一个新的 Document 对象
实例化一个新的`Document`通过添加以下代码行对象：

```csharp
Document doc = new Document();
```

## 第 5 步：向文档添加页面
通过使用向文档添加新页面`Add`的方法`Pages`收藏。在提供的代码中，新页面被分配给变量`page`.

```csharp
Page page = doc.Pages.Add();
```

## 第 6 步：使用 HTML 内容创建一个 HtmlFragment
实例化一个`HtmlFragment`对象并提供所需的 HTML 内容。在提供的代码中，HTML 内容被分配给变量`titel`.您可以根据需要修改 HTML 内容。

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## 第七步：设置保证金信息
如有必要，调整 HTML 片段的底部和顶部边距。在提供的代码中，底部边距设置为 10，顶部边距设置为 200。

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## 第 8 步：将 HtmlFragment 添加到页面
添加`HtmlFragment`反对页面的段落集合。

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## 第 9 步：保存 PDF 文档
使用保存 PDF 文档`Save`的方法`Document`目的。指定您在步骤 3 中设置的输出文件路径。

```csharp
doc.Save(dataDir);
```

## 第 10 步：显示成功消息
显示一条成功消息以及保存 PDF 文件的路径。

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 添加 HTMLUsing DOM 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化文档对象
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Page page = doc.Pages.Add();
//使用 HTML contnets 实例化 HtmlFragment
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
//设置底部边距信息
titel.Margin.Bottom = 10;
//设置上边距信息
titel.Margin.Top = 200;
//将 HTML 片段添加到页面的段落集合
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
//保存PDF文件
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## 结论
您已经在 Aspose.PDF for .NET 中使用 DOM 成功添加了 HTML 内容。现在可以在指定的输出文件路径中找到生成的 PDF 文件。