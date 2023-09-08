---
title: 在 PDF 文件中添加后续行缩进
linktitle: 在 PDF 文件中添加后续行缩进
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中的文本中添加后续行缩进。
type: docs
weight: 60
url: /zh/net/programming-with-text/add-subsequent-lines-indent/
---
本教程将指导您完成使用 Aspose.PDF for .NET 在 PDF 文件中的文本中添加后续行缩进的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具备以下条件：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 等包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入所需的命名空间
在要添加后续行缩进的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：设置文档目录
在代码中，找到显示以下内容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`以及存储文档的目录的路径。

## 步骤 4：创建一个新的 Document 对象
实例化一个新的`Document`对象，添加以下代码行：

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## 步骤 5：向文档添加页面
使用以下命令将新页面添加到文档中`Add`的方法`Pages`收藏。在提供的代码中，新页面被分配给变量`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## 步骤 6：创建一个带有后续行缩进的 TextFragment
实例化一个`TextFragment`对象并提供所需的文本。在提供的代码中，文本被分配给变量`text`。然后，初始化`TextFormattingOptions`为了`TextFragment`并指定`SubsequentLinesIndent`价值。

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## 第7步：将TextFragment添加到页面
添加`TextFragment`对象页面的段落集合。

```csharp
page.Paragraphs.Add(text);
```

## 步骤 8：对其他行重复步骤 6 和 7
要添加具有相同缩进的后续行，请对每行重复步骤 6 和 7。根据需要更新文本内容。

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## 第9步：保存PDF文档
使用以下命令保存 PDF 文档`Save`的方法`Document`目的。指定输出文件路径。

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### 使用 Aspose.PDF for .NET 添加后续行缩进的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建新文档对象
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//为文本片段初始化 TextFormattingOptions 并指定 SubsequentLinesIndent 值
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 结论
您已使用 Aspose.PDF for .NET 成功向文本添加了后续行缩进。现在可以在指定的输出文件路径中找到生成的 PDF 文件。

### 常见问题解答

#### 问：本教程的重点是什么？

答：本教程提供了有关如何使用 Aspose.PDF for .NET 库向 PDF 文件中的文本添加后续行缩进的全面指南。它包括 C# 源代码示例来说明实现此目的所需的步骤。

#### 问：本教程需要导入哪些命名空间？

答：在要添加后续行缩进的代码文件中，在文件开头导入以下命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### 问：如何指定文档目录？

 A：在代码中，找到行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

#### 问：如何创建 Document 对象？

答：在第 4 步中，您将实例化一个新的`Document`使用以下代码行对象：

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### 问：如何向文档添加页面？

答：在第 5 步中，您将使用`Add`的方法`Pages`收藏：

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### 问：如何为文本添加后续行缩进？

答：在第 6 步中，您将创建一个`TextFragment`对象并为其分配所需的文本。然后，您将初始化`TextFormattingOptions`为了`TextFragment`并指定`SubsequentLinesIndent`价值：

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### 问：如何将 TextFragment 添加到 PDF 文档中？

答：在第 7 步中，您将添加`TextFragment`目的 （`text`到页面的段落集合：

```csharp
page.Paragraphs.Add(text);
```

#### 问：我可以对其他线路重复此过程吗？

答：是的，在第 8 步中，您可以通过创建新的行来对具有相同缩进的其他行重复该过程`TextFragment`对象并将它们添加到页面的段落集合中。

#### 问：如何保存生成的 PDF 文档？

 A：添加带有后续行缩进的文本后，使用`Save`的方法`Document`保存 PDF 文档的对象：

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### 问：本教程的主要内容是什么？

答：通过学习本教程，您已经成功学习了如何使用 Aspose.PDF for .NET 添加后续行缩进来增强 PDF 文档中文本的可读性。此技术可用于各种类型的文档和报告。