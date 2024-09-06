---
title: 在 PDF 文件中的文本中添加工具提示
linktitle: 在 PDF 文件中的文本中添加工具提示
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 向 PDF 文件中的文本添加工具提示。
type: docs
weight: 90
url: /zh/net/programming-with-text/add-tooltip-to-text/
---
本教程将指导您使用 Aspose.PDF for .NET 向 PDF 文件中的文本添加工具提示的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
开始之前，请确保您已准备好以下物品：

- 您的机器上安装的 Visual Studio 或任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它，或者使用 NuGet 等包管理器来安装它。

## 步骤 1：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 步骤 2：导入所需的命名空间
在您想要向文本添加工具提示的代码文件中，在文件顶部添加以下使用指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## 步骤3：设置文档目录
在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用存储文档的目录路径。

## 步骤 4：创建包含文本的示例文档
创建新的`Document`对象并添加带有文本片段的页面。在提供的代码中，两个文本片段与相应的工具提示文本一起添加到文档中。

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## 步骤 5：打开文档并找到文本片段
使用加载创建的文档`Document`构造函数并找到需要工具提示的文本片段`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## 步骤 6：向文本片段添加工具提示
循环遍历提取的文本片段并在其位置创建不可见的按钮。将所需的工具提示文本分配给`AlternateName`的财产`ButtonField`将按钮字段添加到文档的表单中。

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## 步骤 7：重复上述步骤，添加带有长工具提示的其他文本片段
对于带有长工具提示的文本片段，重复步骤 5 和 6。相应地修改搜索条件和工具提示文本。

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## 步骤8：保存修改后的文档
使用`Save`方法`Document`目的。

```csharp
document. Save(outputFile);
```

### 使用 Aspose.PDF for .NET 添加工具提示到文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
//创建带有文本的示例文档
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
//打开带有文本的文档
Document document = new Document(outputFile);
//创建 TextAbsorber 对象来查找与正则表达式匹配的所有短语
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
//接受文件页面的吸收器
document.Pages.Accept(absorber);
//获取提取的文本片段
TextFragmentCollection textFragments = absorber.TextFragments;
//循环遍历片段
foreach (TextFragment fragment in textFragments)
{
	//在文本片段位置创建隐形按钮
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//AlternateName 值将由查看器应用程序显示为工具提示
	field.AlternateName = "Tooltip for text.";
	//向文档添加按钮字段
	document.Form.Add(field);
}
//接下来将是一个非常长的工具提示的样本
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//设置非常长的文本
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
//保存文档
document.Save(outputFile);
```

## 结论
您已成功使用 Aspose.PDF for .NET 将工具提示添加到 PDF 文档中的文本。现在可以在指定的输出文件路径中找到生成的 PDF 文件。

## 常见问题解答

#### 问：本教程的重点是什么？

答：本教程重点介绍如何使用 Aspose.PDF for .NET 库在 PDF 文件中的文本中添加工具提示。提供的 C# 源代码演示了实现此目的所需的步骤。

#### 问：本教程需要导入哪些命名空间？

答：在您想要向文本添加工具提示的代码文件中，在文件开头导入以下命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### 问：如何指定文档目录？

答：在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

#### 问：如何创建带有文本的示例文档？

答：在第 4 步中，您将创建一个新的`Document`对象并添加带有文本片段的页面。提供的代码添加了两个带有各自工具提示文本的文本片段。

#### 问：如何打开文档并找到文本片段？

答：在第 5 步中，您将使用`Document`构造函数并使用`TextFragmentAbsorber`.

#### 问：如何向文本片段添加工具提示？

答：在第 6 步中，您将循环遍历提取的文本片段并在其位置创建不可见的按钮。工具提示文本将分配给`AlternateName`的财产`ButtonField`，该内容被添加到文档的表单中。

#### 问：如何对带有长工具提示的附加文本片段重复此过程？

答：对于具有长工具提示的文本片段，重复步骤 5 和 6。相应地修改搜索条件和工具提示文本。

#### 问：如何保存修改后的文档？

答：在第 8 步中，您将使用`Save`方法`Document`目的。

#### 问：本教程的主要内容是什么？

答：通过本教程，您学会了如何使用 Aspose.PDF for .NET 向文本添加工具提示来增强 PDF 文档。这可以在读者与 PDF 内容交互时为他们提供有价值的附加信息。