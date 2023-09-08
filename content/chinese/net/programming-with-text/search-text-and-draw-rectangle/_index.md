---
title: 搜索文本并绘制矩形
linktitle: 搜索文本并绘制矩形
second_title: Aspose.PDF for .NET API 参考
description: 了解如何在 PDF 中搜索文本、在找到的文本周围绘制矩形以及使用 Aspose.PDF for .NET 保存修改后的文档。
type: docs
weight: 460
url: /zh/net/programming-with-text/search-text-and-draw-rectangle/
---
本教程介绍如何使用 Aspose.PDF for .NET 搜索 PDF 文档中的特定文本，在找到的文本周围绘制矩形，然后保存修改后的文档。提供的 C# 源代码逐步演示了该过程。

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## 第三步：设置文档目录路径

使用以下命令设置文档目录的路径`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第 4 步：加载 PDF 文档

使用加载 PDF 文档`Document`班级：

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

代替`"SearchAndGetTextFromAll.pdf"`与您的 PDF 文件的实际名称。

## 第5步：创建一个TextFragmentAbsorber

创建一个`TextFragmentAbsorber`对象查找输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

代替`@"[\S]+"`与您想要的正则表达式模式。

## 第 6 步：启用正则表达式搜索

通过设置启用正则表达式搜索`TextSearchOptions`吸收体的特性：

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## 第7步：在所有页面上搜索

接受文档所有页面的吸收器：

```csharp
document.Pages.Accept(textAbsorber);
```

## 第 8 步：在找到的文本周围画一个矩形

创建一个`PdfContentEditor`对象并循环检索到的文本片段，在每个文本片段周围绘制一个矩形：

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## 步骤9：保存修改后的文档

保存修改后的文档：

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

确保更换`"SearchTextAndDrawRectangle_out.pdf"`与所需的输出文件名。

### 使用 Aspose.PDF for .NET 搜索文本和绘制矩形的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//创建 TextAbsorber 对象以查找与正则表达式匹配的所有短语
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已经成功学习了如何在 PDF 文档中搜索特定文本、在找到的文本周围绘制矩形以及使用 Aspose.PDF for .NET 保存修改后的文档。本教程提供了从设置项目到执行所需操作的分步指南。现在，您可以将此代码合并到您自己的 C# 项目中，以操作 PDF 文件中的文本和绘制矩形。

### 常见问题解答

#### 问：“搜索文本并绘制矩形”教程的目的是什么？

答：“搜索文本并绘制矩形”教程旨在指导用户使用 Aspose.PDF 库 for .NET 在 PDF 文档中搜索特定文本，在找到的文本段周围绘制矩形，并保存修改后的内容。文档。本教程提供了详细的说明和 C# 代码示例来说明该过程的每个步骤。

#### 问：本教程如何帮助您在 PDF 文档中的特定文本周围绘制矩形？

答：本教程提供了有关如何在 PDF 文档中的特定文本段周围定位和绘制矩形的全面指南。它演示了设置项目、加载 PDF 文档、启用正则表达式搜索、在找到的文本段周围绘制矩形以及保存修改后的 PDF 的过程。

#### 问：学习本教程需要什么先决条件？

答：在开始本教程之前，您应该对 C# 编程语言有基本的了解。此外，您需要安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

#### 问：如何设置我的项目来遵循本教程？

答：首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目。然后，将对 Aspose.PDF for .NET 库的引用添加到您的项目中。这将使您能够使用库的功能来操作 PDF 文档。

#### 问：我可以使用本教程在特定文本周围绘制矩形吗？

答：是的，本教程的重点是在 PDF 文档中的特定文本段周围绘制矩形。它演示了如何使用正则表达式找到所需的文本，在识别的文本段周围创建矩形，以及保存修改后的 PDF。

#### 问：如何指定要搜索的文本并在其周围绘制矩形？

答：要指定要搜索的文本并在其周围绘制矩形，请创建一个`TextFragmentAbsorber`对象并使用设置其模式`Text`范围。替换默认模式`@"[\S]+"`在教程的代码中添加您所需的正则表达式模式。

#### 问：如何启用文本的正则表达式搜索？

 A：通过创建一个来启用正则表达式搜索`TextSearchOptions`对象并将其值设置为`true`。将此对象分配给`TextSearchOptions`的财产`TextFragmentAbsorber`实例。这可确保在文本搜索期间使用正则表达式模式。

#### 问：如何在找到的文本周围绘制矩形？

 A：使用识别文本段后`TextFragmentAbsorber`，本教程提供了一个循环来迭代这些段。对于每个文本段，本教程演示了如何使用以下命令在其周围创建一个矩形：`DrawBox`方法并指定矩形的外观。

#### 问：保存修改后的绘制矩形的PDF的步骤是什么？

答：在所需的文本段周围绘制矩形后，使用`Document`班级的`Save`方法保存修改后的文档。本教程的示例代码展示了如何保存编辑后的 PDF 并显示成功消息。

#### 问：我可以自定义绘制矩形的外观吗？

答：是的，您可以自定义绘制矩形的外观。在本教程的示例代码中，`DrawBox`方法用于创建矩形。您可以修改颜色、样式和厚度等属性来自定义绘制矩形的外观。