---
title: 嵌入标准 Type 1 字体
linktitle: 嵌入标准 Type 1 字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中嵌入标准 Type 1 字体。
type: docs
weight: 140
url: /zh/net/programming-with-text/embed-standard-type-1fonts/
---

本教程将指导您使用 Aspose.PDF for .NET 在 PDF 文档中嵌入标准 Type 1 字体。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具有以下内容：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- .NET 库的 Aspose.PDF。您可以从 Aspose 官方网站下载它，或者使用像 NuGet 这样的包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入所需的命名空间
在要嵌入标准 Type 1 字体的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
```

## 第三步：设置文档目录
在代码中，找到显示的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并更换`"YOUR DOCUMENT DIRECTORY"`与存储文档的目录的路径。

## 第 4 步：加载现有的 PDF 文档
使用`Document`构造函数并将路径传递到输入 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## 第 5 步：设置 EmbedStandardFonts 属性
设置`EmbedStandardFonts`文档的属性`true`为了启用嵌入标准 Type 1 字体。

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## 第 6 步：在每个页面中嵌入字体
遍历 PDF 文档的每一页并检查字体是否已嵌入。如果没有，设置`IsEmbedded`财产给`true`嵌入字体。

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## 步骤 7：保存更新后的 PDF 文档
使用保存更新的 PDF 文档`Save`的方法`Document`对象，指定输出文件路径。

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### 使用 Aspose.PDF for .NET 的 Embed Standard Type 1Fonts 示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载现有的 PDF 文档
Document pdfDocument = new Document(dataDir + "input.pdf");
//设置文档的 EmbedStandardFonts 属性
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			//检查字体是否已经嵌入
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## 结论
您已经使用 Aspose.PDF for .NET 成功地将标准 Type 1 字体嵌入到 PDF 文档中。更新后的带有嵌入字体的 PDF 文件已保存在指定的输出文件路径中。