---
title: 提取 PDF 文件中的段落
linktitle: 提取 PDF 文件中的段落
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 提取 PDF 文件中的段落。
type: docs
weight: 160
url: /zh/net/programming-with-text/extract-paragraphs/
---
本教程将指导您使用 Aspose.PDF for .NET 提取 PDF 文件中的段落。提供的 C# 源代码演示了必要的步骤。

## 要求
开始之前，请确保您已准备好以下物品：

- 您的机器上安装的 Visual Studio 或任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它，也可以使用 NuGet 等包管理器来安装它。

## 步骤 1：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 步骤 2：导入所需的命名空间
在要提取段落的代码文件中，在文件顶部添加以下使用指令：

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## 步骤3：设置文档目录
在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用存储文档的目录路径。

## 步骤 4：打开 PDF 文档
使用打开现有 PDF 文档`Document`构造函数并将路径传递给输入的 PDF 文件。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 步骤 5：提取段落
实例化`ParagraphAbsorber`类并使用其`Visit`方法从文档中提取段落。

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## 步骤 6：遍历段落
循环遍历提取的段落以访问文本内容。使用嵌套循环遍历每个段落中的部分和行。

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### 使用 Aspose.PDF for .NET 提取段落的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开现有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
//实例化 ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## 结论
您已成功使用 Aspose.PDF for .NET 从 PDF 文档中提取段落。提取的段落已显示在控制台窗口中。

### 常见问题解答

#### 问：本教程的目的是什么？

答：本教程旨在指导您使用 Aspose.PDF for .NET 从 PDF 文件中提取段落的过程。随附的 C# 源代码提供了完成此任务的实用步骤。

#### 问：我应该导入哪些命名空间？

答：在您打算提取段落的代码文件中，在文件开头包含以下使用指令：

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### 问：如何指定文档目录？

答：找到该线`string dataDir = "YOUR DOCUMENT DIRECTORY";`在代码中替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

#### 问：如何打开现有的 PDF 文档？

答：在第 4 步中，您将使用`Document`构造函数并提供输入 PDF 文件的路径。

#### 问：如何从文档中提取段落？

答：第 5 步涉及创建`ParagraphAbsorber`类并使用其`Visit`方法从 PDF 文档中提取段落。

#### 问：如何迭代提取的段落？

答：第 6 步将引导您循环遍历提取的段落。使用嵌套循环遍历每个段落中的节和行，最终访问并显示文本内容。

#### 问：本教程的重点是什么？

答：通过本教程，您学会了如何使用 Aspose.PDF for .NET 从 PDF 文档中提取段落。提取的段落已显示在控制台窗口中，为您提供了有关文档内容结构的宝贵见解。