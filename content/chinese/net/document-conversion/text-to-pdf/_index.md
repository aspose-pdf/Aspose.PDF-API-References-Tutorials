---
title: 文本转PDF
linktitle: 文本转PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将文本文件简单高效地转换为 PDF。
type: docs
weight: 300
url: /zh/net/document-conversion/text-to-pdf/
---
本教程将引导您完成使用 Aspose.PDF for .NET 将文本文件转换为 PDF 文件的步骤。 Aspose.PDF 提供了一个简单而有效的解决方案，用于将纯文本转换为 PDF，同时保留文本格式和演示文稿。请按照以下步骤执行此转换。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- 您的系统上安装了适用于 .NET 的 Aspose.PDF 库。
- 开发环境，例如 Visual Studio。

## 第一步：读取文本文件
第一步是使用以下命令读取文本文件的内容`StreamReader`班级。使用以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//读取文本文件
TextReader tr = new StreamReader(dataDir + "log.txt");
```

一定要更换`"YOUR DOCUMENTS DIRECTORY"`与文本文件所在的实际目录。

## 第 2 步：创建 PDF 文档
第二步是创建一个`Document`代表最终 PDF 文档的对象。使用以下代码：

```csharp
//创建文档对象
Document doc = new Document();
```

## 步骤 3：向文档添加文本
第三步，将阅读的文本添加到PDF文档的页面中。使用以下代码：

```csharp
//向文档添加新页面
Page page = doc.Pages.Add();

//创建一个 TextFragment 对象并将读取的文本作为参数传递
TextFragment text = new TextFragment(tr.ReadToEnd());

//将文本段落添加到页面
page.Paragraphs.Add(text);
```

## 步骤 4：保存 PDF 文件
最后，通过指定所需的路径和文件名来保存生成的 PDF 文件。使用以下代码：

```csharp
//保存生成的 PDF 文件
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

请务必为生成的 PDF 文件指定所需的路径和文件名。

### 使用 Aspose.PDF for .NET 的文本转 PDF 示例源代码

```csharp
try
{
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//读取源文本文件
	TextReader tr = new StreamReader(dataDir + "log.txt");

	//通过调用其空构造函数来实例化 Document 对象
	Document doc = new Document();

	//在文档的页面集合中添加新页面
	Page page = doc.Pages.Add();

	//创建 TextFragmet 的实例并将文本从 reader 对象传递到其构造函数作为参数
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	//在段落集合中添加新的文本段落并传递 TextFragment 对象
	page.Paragraphs.Add(text);

	//保存生成的 PDF 文件
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 将文本文件转换为 PDF 文件。按照上面给出的步骤，您可以轻松地执行此转换。使用此方法将文本文件转换为 PDF，并享受 Aspose.PDF 的灵活性和质量。

### 常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个功能强大的库，使开发人员能够在 C# 应用程序中处理 PDF 文档。它提供各种功能，包括将纯文本转换为 PDF。

#### 问：为什么我要将文本文件转换为 PDF？

答：将文本文件转换为 PDF 格式可以更好地管理、共享和分发文档。 PDF 文件在不同设备和操作系统上提供一致的格式。

#### 问：如何使用 Aspose.PDF for .NET 加载文本文件并将其转换为 PDF？

答：要加载文本文件，您可以使用`StreamReader`类来读取文件的内容。然后，创建一个`Document`代表 PDF 文档的对象。添加一个新页面和一个`TextFragment`包含文本文件中的文本。最后，使用以下命令保存生成的 PDF`Save`的方法`Document`目的。

#### 问：我可以自定义 PDF 中文本的外观吗？

答：是的，Aspose.PDF for .NET 提供了各种选项来自定义生成的 PDF 中文本的外观，例如字体样式、大小、颜色和对齐方式。

#### 问：生成的 PDF 中是否保留文本格式？

答：是的，Aspose.PDF for .NET 在文本到 PDF 转换期间保留文本格式和布局，确保原始内容的准确表示。