---
title: 将 HTML 有序列表添加到文档中
linktitle: 将 HTML 有序列表添加到文档中
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 向文档添加 HTML 有序列表。
type: docs
weight: 30
url: /zh/net/programming-with-text/add-html-ordered-list-into-documents/
---
在本教程中，您将学习如何使用 Aspose.PDF for .NET 库将 HTML 有序列表添加到文档中。提供的代码演示了完成此任务的必要步骤。

## 要求
开始之前，请确保您已准备好以下物品：

- 您的机器上安装的 Visual Studio 或任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它，也可以使用 NuGet 等包管理器来安装它。

## 步骤 1：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 步骤 2：导入所需的命名空间
在要添加 HTML 有序列表的代码文件中，在文件顶部添加以下使用指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 步骤3：设置文档目录和输出文件路径
在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用存储文档的目录路径。

接下来，找到以下行：`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";`并替换`"AddHTMLOrderedListIntoDocuments_out.pdf"`使用您所需的输出 PDF 文件的名称。

## 步骤 4：创建一个新的 Document 对象
实例化一个新的`Document`对象，添加以下代码行：

```csharp
Document doc = new Document();
```

## 步骤 5：使用 HTML 内容创建 HtmlFragment 对象
实例化`HtmlFragment`对象，其中包含要添加到文档的 HTML 内容。在提供的代码中，HTML 内容被分配给变量`t`。您可以根据需要修改HTML内容。

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## 步骤 6：向文档添加页面
使用`Add`方法`Pages`集合。在提供的代码中，新页面被分配给变量`page`.

```csharp
Page page = doc.Pages.Add();
```

## 步骤 7：将 HtmlFragment 添加到页面
添加`HtmlFragment`通过使用`Add`方法`Paragraphs`收藏。

```csharp
page.Paragraphs.Add(t);
```

## 步骤 8：保存 PDF 文档
使用`Save`方法`Document`对象。指定您在步骤 3 中设置的输出文件路径。

```csharp
doc.Save(outFile);
```

### 使用 Aspose.PDF for .NET 将 HTMLOrdered 列表添加到文档中的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//输出文档的路径。
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
//实例化 Document 对象
Document doc = new Document();
//使用相应的 HTML 片段实例化 HtmlFragment 对象
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
//在页面集合中添加页面
Page page = doc.Pages.Add();
//在页面内添加 HtmlFragment
page.Paragraphs.Add(t);
//保存生成的 PDF 文件
doc.Save(outFile);
```

## 结论
您已成功使用 Aspose.PDF for .NET 将 HTML 有序列表添加到文档中。现在可以在指定的输出文件路径中找到生成的 PDF 文件。

请记住根据您的具体要求自定义 HTML 内容并调整代码。

### 常见问题解答

#### 问：本教程的目的是什么？

答：本教程旨在指导您使用 Aspose.PDF for .NET 库将 HTML 有序列表添加到文档中的过程。它提供了分步说明和代码片段来帮助您完成此任务。

#### 问：本教程需要导入哪些命名空间？

答：您需要在代码文件顶部导入以下命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### 问：如何指定文档目录和输出文件路径？

答：在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`替换为文档目录的实际路径。此外，找到以下行`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";`并替换`"AddHTMLOrderedListIntoDocuments_out.pdf"`使用您想要的输出 PDF 文件名。

#### 问：我可以自定义添加到文档的 HTML 内容吗？

答：当然可以！在第 5 步中，你将创建一个`HtmlFragment`对象命名`t`包含 HTML 内容。您可以修改反引号内的 HTML 内容以满足您的要求。

#### 问：如何将 HTML 有序列表添加到文档的页面中？

答：在第 7 步中，您将添加`HtmlFragment`目的 （`t` ）使用`Add`方法`Paragraphs`集合。这将无缝地将 HTML 有序列表集成到文档中。

#### 问：如何保存生成的 PDF 文档？

答：添加 HTML 内容并将其排列在页面上后，您可以使用`Save`方法`Document`对象。请确保提供您之前设置的正确输出文件路径。

#### Q：能否提供一下示例源码的概要，供参考？

答：当然可以！以下是本教程提供的示例源代码的摘要版本：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### 问：本教程的重点是什么？

答：通过本教程，您已成功学会了如何利用 Aspose.PDF for .NET 库将 HTML 有序列表合并到文档中。这些新知识可用于增强文档创建和操作过程。