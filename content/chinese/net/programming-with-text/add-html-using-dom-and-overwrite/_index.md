---
title: 使用 DOM 和 PDF 覆盖添加 HTML
linktitle: 使用 DOM 添加 HTML 并覆盖
second_title: Aspose.PDF for .NET API 参考
description: 了解如何在 Aspose.PDF for .NET 中使用 DOM 和 PDF 覆盖添加 HTML 内容。
type: docs
weight: 50
url: /zh/net/programming-with-text/add-html-using-dom-and-overwrite/
---
本教程将指导您完成在 Aspose.PDF for .NET 中使用 DOM（文档对象模型）添加 HTML 内容的过程。此外，您还将学习如何覆盖 HTML 内容的样式。提供的 C# 源代码演示了必要的步骤。

## 要求
开始之前，请确保您已准备好以下物品：

- 您的机器上安装的 Visual Studio 或任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它，或者使用 NuGet 等包管理器来安装它。

## 步骤 1：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 步骤 2：导入所需的命名空间
在要添加 HTML 内容的代码文件中，在文件顶部添加以下使用指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 步骤3：设置文档目录和输出文件路径
在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用存储文档的目录路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 4：创建一个新的 Document 对象
实例化一个新的`Document`对象，添加以下代码行：

```csharp
Document doc = new Document();
```

## 步骤 5：向文档添加页面
使用`Add`方法`Pages`集合。在提供的代码中，新页面被分配给变量`page`.

```csharp
Page page = doc.Pages.Add();
```

## 步骤 6：使用 HTML 内容创建 HtmlFragment
实例化`HtmlFragment`对象并提供所需的 HTML 内容。在提供的代码中，HTML 内容被分配给变量`title`。您可以根据需要修改HTML内容。

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## 步骤 7：覆盖 HTML 内容的样式
要覆盖 HTML 内容的样式，您可以修改`TextState`的属性`HtmlFragment`对象。在提供的代码中，字体系列更改为“Arial”，字体大小设置为 20。

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## 步骤8：设置边距信息
如果需要，请调整 HTML 片段的底部和顶部边距。在提供的代码中，底部边距设置为 10，顶部边距设置为 400。

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## 步骤 9：将 HtmlFragment 添加到页面
添加`HtmlFragment`反对页面的段落集合。

```csharp
page.Paragraphs.Add(title);
```

## 步骤 10：保存 PDF 文档
使用`Save`方法`Document`对象。指定您在步骤 3 中设置的输出文件路径。

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 添加 HTML、使用 DOM 和覆盖的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化 Document 对象
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Page page = doc.Pages.Add();
//使用 HTML 内容实例化 HtmlFragment
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//字体系列从“Verdana”将重置为“Arial”
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
//设置下边距信息
title.Margin.Bottom = 10;
//设置顶部边距信息
title.Margin.Top = 400;
//将 HTML 片段添加到页面的段落集合中
page.Paragraphs.Add(title);
//保存 PDF 文件
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
//保存 PDF 文件
doc.Save(dataDir);
```

## 结论
您已成功使用 Aspose.PDF for .NET 中的 DOM 添加 HTML 内容并覆盖 HTML 内容的样式。现在可以在指定的输出文件路径中找到生成的 PDF 文件。

### 常见问题解答

#### 问：本教程的重点是什么？

答：本教程旨在引导您完成使用 Aspose.PDF for .NET 中的文档对象模型 (DOM) 将 HTML 内容添加到 PDF 文档的过程。此外，您还将学习如何覆盖 HTML 内容的样式，从而允许您自定义其外观。本教程提供了 C# 源代码片段来演示所需的步骤。

#### 问：本教程需要导入哪些命名空间？

答：在您打算添加 HTML 内容的代码文件中，在文件开头导入以下命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### 问：如何指定文档目录和输出文件路径？

答：在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

#### 问：如何创建 Document 对象？

答：在第 4 步中，你将实例化一个新的`Document`对象使用以下代码行：

```csharp
Document doc = new Document();
```

#### 问：如何在文档中添加页面？

答：在第 5 步中，您将使用`Add`方法`Pages`收藏：

```csharp
Page page = doc.Pages.Add();
```

#### 问：如何使用 DOM 设置 HTML 内容？

答：在第 6 步中，你将创建一个`HtmlFragment`对象并为其分配所需的 HTML 内容。HTML 内容被分配给变量`title`：

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### 问：如何覆盖 HTML 内容的样式？

答：在第 7 步中，您将通过修改`TextState`的属性`HtmlFragment`对象。例如，您可以将字体系列更改为“Arial”，并将字体大小设置为 20：

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### 问：我可以调整 HTML 内容的边距吗？

答：是的，在第 8 步中，您可以根据需要调整 HTML 片段的底部和顶部边距：

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### 问：如何将 HtmlFragment 添加到 PDF 文档？

答：在第 9 步中，您将添加`HtmlFragment`目的 （`title`到页面的段落集合：

```csharp
page.Paragraphs.Add(title);
```

#### 问：如何保存生成的 PDF 文档？

答：添加 HTML 内容并自定义其样式后，使用`Save`方法`Document`保存PDF文档的对象：

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### 问：本教程的重点是什么？

答：通过本教程，您已成功学会了如何使用 Aspose.PDF for .NET 中的文档对象模型 (DOM) 整合 HTML 内容。此外，您还能够覆盖样式以定制生成的 PDF 文档中 HTML 内容的外观。