---
title: 获取超链接目标
linktitle: 获取超链接目标
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文件中提取超链接目标。
type: docs
weight: 60
url: /zh/net/programming-with-links-and-actions/get-hyperlink-destinations/
---

Aspose.PDF for .NET 是一个功能强大的库，用于使用 C# 编程语言从 PDF 文件中操作和提取信息。在本教程中，我们将专注于使用 Aspose.PDF for .NET 从 PDF 文件中提取超链接目标。

## 先决条件

在开始之前，请确保您具备以下条件：

- 集成开发环境 (IDE)，例如 Visual Studio。
- 安装在您机器上的 .NET 的 Aspose.PDF 库。

## 第一步：搭建开发环境

在开始编写代码之前，您需要通过在您喜欢的 IDE 中创建一个新的 C# 项目来设置您的开发环境。

## 第 2 步：导入 Aspose.PDF 引用

要使用 Aspose.PDF for .NET，您需要将适当的引用添加到您的项目中。按照以下步骤导入必要的参考文献：

1. 在您的项目中，右键单击“引用”并选择“添加引用”。
2. 在“添加引用”窗口中，找到并选择 Aspose.PDF for .NET 的 DLL 文件。
3. 单击“确定”将引用导入到您的项目中。

## 第 3 步：加载 PDF 文件

在您可以提取超链接目标之前，您必须将 PDF 文件加载到您的应用程序中。使用以下代码加载 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载 PDF 文件
Document document = new Document(dataDir + "input.pdf");
```

请务必指定正确的文档目录路径和要处理的 PDF 文件。

## 第 4 步：浏览文档的页面

现在 PDF 文件已加载，您需要浏览文档的所有页面。这将使你得到

ir 每个页面上的超链接注释。使用以下代码遍历文档的页面：

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     //获取特定页面的链接注解
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     //创建一个列表来存储所有链接
     IList<Annotation> list = selector. Selected;
     //遍历列表中的每个项目
     foreach(LinkAnnotation a in list)
     {
         //打印目标网址
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

此代码遍历文档的每一页并选择每一页上存在的超链接注释。然后它将这些注释存储在列表中并打印每个链接的目标 URL。

## 步骤 5：获取超链接目标

最后一步是从超链接注释中提取超链接目标。以下代码向您展示了如何操作：

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         //根据需要使用目的地
     }
}
```

在此代码中，我们从链接注释中获取每个超链接目标并将目标存储在变量中。然后，您可以根据需要在您的应用程序中使用此目的地。

### 使用 Aspose.PDF for .NET 获取超链接目标的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载 PDF 文件
	Document document = new Document(dataDir + "input.pdf");
	//遍历PDF的所有页面
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		//从特定页面获取链接注释
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		//创建包含所有链接的列表
		IList<Annotation> list = selector.Selected;
		//遍历列表中的单个项目
		foreach (LinkAnnotation a in list)
		{
			//打印目标 URL
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```