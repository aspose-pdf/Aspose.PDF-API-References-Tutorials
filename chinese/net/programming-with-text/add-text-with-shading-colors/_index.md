---
title: 添加带有底纹颜色的文本
linktitle: 添加带有底纹颜色的文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将带有底纹颜色的文本添加到 PDF 文档中。
type: docs
weight: 80
url: /zh/net/programming-with-text/add-text-with-shading-colors/
---

本教程将指导您完成使用 Aspose.PDF for .NET 添加带有底纹颜色的文本的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具备以下条件：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 等包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入所需的命名空间
在要添加带有底纹颜色的文本的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## 第三步：设置文档目录
在代码中，找到显示以下内容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`以及存储文档的目录的路径。

## 第 4 步：加载 PDF 文档
使用以下命令加载现有 PDF 文档`Document`构造函数并提供文档文件的路径。

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     //代码放在这里...
}
```

## 第五步：找到要修改的文字
使用`TextFragmentAbsorber`在文档中查找所需的文本。在提供的代码中，它查找文本“Lorem ipsum”。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## 第6步：设置文本的底纹颜色
创建一个新的`Color`具有图案色彩空间的对象并指定渐变着色颜色。将此颜色分配给`ForegroundColor`的财产`TextState`的`TextFragment`目的。

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## 第 7 步：应用其他文本格式（可选）
您可以通过修改文本片段的属性，对文本片段应用其他格式，例如下划线。`TextState`目的。

```csharp
textFragment.TextState.Underline = true;
```

## 步骤8：保存修改后的PDF文档
使用以下命令保存修改后的 PDF 文档`Save`的方法`Document`目的。

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### 使用 Aspose.PDF for .NET 添加带有底纹颜色的文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	//使用图案色彩空间创建新颜色
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## 结论
您已使用 Aspose.PDF for .NET 成功将带有底纹颜色的文本添加到 PDF 文档中。现在可以在指定的输出文件路径中找到生成的 PDF 文件。