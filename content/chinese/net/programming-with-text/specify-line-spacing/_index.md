---
title: 在 PDF 文件中指定行距
linktitle: 在 PDF 文件中指定行距
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中指定行距。
type: docs
weight: 510
url: /zh/net/programming-with-text/specify-line-spacing/
---
本教程介绍如何使用 Aspose.PDF for .NET 在 PDF 文件中指定行距。提供的 C# 源代码逐步演示了该过程。

## 先决条件

在继续学习本教程之前，请确保您具备以下条件：

- C# 编程语言的基础知识。
- 安装了 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

## 第 1 步：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入必要的命名空间

在 C# 文件的开头添加以下 using 指令以导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 第三步：设置文档目录路径

使用以下命令设置文档目录的路径`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第 4 步：加载输入的 PDF 文件

使用以下命令加载输入 PDF 文件`Document`班级：

```csharp
Document doc = new Document();
```

## 第 5 步：创建 TextFormattingOptions

创建一个`TextFormattingOptions`对象并将行距模式设置为`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## 第 6 步：创建一个 TextFragment

创建一个`TextFragment`对象并指定文本内容：

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## 第7步：加载字体文件（可选）

如果要在文本中使用特定字体，请将 TrueType 字体文件加载到`FileStream`目的：

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

代替`"HPSimplified.TTF"`与实际的字体文件名。

## 第8步：指定文本位置和行间距

设置文本片段的位置并分配`TextFormattingOptions`到`TextState.FormattingOptions`财产：

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## 步骤 9：将文本添加到文档中

将文本片段添加到文档中，方法是将其附加到`TextBuilder`或直接到页面`Paragraphs`收藏：

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## 第10步：保存生成的PDF文档

保存修改后的PDF文档：

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

确保更换`"SpecifyLineSpacing_out.pdf"`与所需的输出文件名。

### 使用 Aspose.PDF for .NET 指定行距的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
//加载输入 PDF 文件
Document doc = new Document();
//使用 LineSpacingMode.FullSize 创建 TextFormattingOptions
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
//为文档第一页创建文本生成器对象
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
//使用示例字符串创建文本片段
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	//将 TrueType 字体加载到流对象中
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//设置文本字符串的字体名称
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//指定文本片段的位置
		textFragment.Position = new Position(100, 600);
		//将当前片段的 TextFormattingOptions 设置为预定义（指向 LineSpacingMode.FullSize）
		textFragment.TextState.FormattingOptions = formattingOptions;
		//将文本添加到 TextBuilder，以便可以将其放置在 PDF 文件上
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	//保存生成的 PDF 文档
	doc.Save(dataDir);
}
```

## 结论

恭喜！您已成功学习如何使用 Aspose.PDF for .NET 在 PDF 文档中指定行距。本教程提供了从设置项目到保存修改后的文档的分步指南。现在，您可以将此代码合并到您自己的 C# 项目中，以自定义 PDF 文件中文本的行距。

### 常见问题解答

#### 问：“指定 PDF 文件中的行距”教程的目的是什么？

答：“在 PDF 文件中指定行距”教程旨在指导用户如何使用 .NET 的 Aspose.PDF 库自定义 PDF 文档中文本的行距。本教程提供分步说明和 C# 代码示例来演示该过程。

#### 问：本教程如何帮助指定 PDF 文档中的行间距？

答：本教程帮助用户了解如何利用 Aspose.PDF for .NET 的功能来指定 PDF 文档中文本的行距。通过遵循提供的步骤和代码示例，用户可以根据自己的喜好调整行间距。

#### 问：学习本教程需要什么先决条件？

答：在开始本教程之前，您应该对 C# 编程语言有基本的了解。此外，您需要安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

#### 问：如何设置我的项目来遵循本教程？

答：首先，在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。这使您能够利用该库的功能来处理 PDF 文档和自定义行距。

#### 问：我可以使用本教程指定任何类型文本的行间距吗？

答：是的，本教程提供了如何使用 Aspose.PDF for .NET 为 PDF 文档中的任何文本内容指定行距的说明。您可以使用提供的代码示例根据您的需要调整文本的行距。

#### Q：教程中如何指定行距模式？

答：本教程演示了如何创建`TextFormattingOptions`对象并设置其`LineSpacing`财产给`TextFormattingOptions.LineSpacingMode.FullSize`。此模式指定文本内容的整行间距。

#### 问：如何加载文本的特定字体？

答：如果您希望在文本内容中使用特定字体，本教程提供了如何将 TrueType 字体文件加载到`FileStream`对象并将其设置为字体`TextFragment`。这使您能够自定义文本的字体及其行距。

#### 问：如何自定义 PDF 文档中文本的位置？

 A：要自定义文本的位置，请创建一个`TextFragment`对象并设置其`Position`属性到所需的坐标（X 和 Y）。这使您可以控制文本在 PDF 文档中的放置位置。

#### 问：我可以将这些行间距修改应用到现有 PDF 文档吗？

答：是的，您可以修改现有 PDF 文档中文本的行距。本教程演示了如何创建`TextFragment`以指定的行距和位置，然后将其添加到页面的`Paragraphs`收藏。