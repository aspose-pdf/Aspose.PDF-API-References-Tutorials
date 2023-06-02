---
title: 嵌入字体
linktitle: 嵌入字体
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 在 PDF 文件中嵌入字体。确保您的文档在任何设备上都能正确显示。
type: docs
weight: 120
url: /zh/net/programming-with-document/embedfont/
---

在本教程中，我们将讨论如何使用 Aspose.PDF for .NET 在 PDF 文件中嵌入字体。 Aspose.PDF for .NET 是一个功能强大的库，允许开发人员以编程方式创建、编辑和操作 PDF 文档。这个库提供了广泛的功能来处理 PDF 文档，包括添加文本、图像、表格等等。在 PDF 文件中嵌入字体是开发人员的常见要求，他们希望确保 PDF 文件在不同设备上正确显示，而不管这些设备上是否安装了所需的字体。

## 第 1 步：创建一个新的 C# 控制台应用程序
首先，在 Visual Studio 中创建一个新的 C# 控制台应用程序。您可以随意命名。创建项目后，您需要添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入 Aspose.PDF 命名空间
在 C# 文件的顶部添加以下代码行以导入 Aspose.PDF 命名空间：

```csharp
using Aspose.Pdf;
```

## 第 3 步：加载现有的 PDF 文件
要在现有 PDF 文件中嵌入字体，您需要使用 Document 类加载该文件。以下代码演示了如何加载现有的 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

## 第 4 步：遍历所有页面
加载 PDF 文件后，您需要遍历文档中的所有页面。对于每个页面，您需要检查是否使用了任何字体，如果使用了，则需要嵌入这些字体。以下代码演示了如何遍历 PDF 文件中的所有页面并嵌入字体：

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            //检查字体是否已经嵌入
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    //检查表单对象
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                //检查字体是否嵌入
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## 步骤 5：保存 PDF 文档
在 PDF 文件中嵌入所有字体后，您需要保存文档。以下代码演示了如何保存 PDF 文件：

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 的嵌入字体示例源代码

这是使用 Aspose.PDF for .NET 嵌入字体的完整源代码。


```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");

//遍历所有页面
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			//检查字体是否已经嵌入
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	//检查表单对象
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				//检查字体是否嵌入
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## 结论
在本文中，我们讨论了如何使用 Aspose.PDF for .NET 在 PDF 文件中嵌入字体。 Aspose.PDF for .NET 提供了一个简单易用的 API 来处理 PDF 文档，包括添加和嵌入字体。在 PDF 文件中嵌入字体是确保文档在不同设备上正确显示的重要步骤，无论这些设备上是否安装了所需的字体
