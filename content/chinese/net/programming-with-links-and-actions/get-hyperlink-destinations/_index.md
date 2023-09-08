---
title: 获取 PDF 文件中的超链接目标
linktitle: 获取 PDF 文件中的超链接目标
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 提取 PDF 文件中的超链接目标。
type: docs
weight: 60
url: /zh/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET 是一个功能强大的库，用于使用 C# 编程语言操作和提取 PDF 文件中的信息。在本教程中，我们将重点介绍使用 Aspose.PDF for .NET 从 PDF 文件中提取超链接目标。

## 先决条件

在开始之前，请确保您具备以下条件：

- 集成开发环境 (IDE)，例如 Visual Studio。
- 您的计算机上安装了适用于 .NET 的 Aspose.PDF 库。

## 第一步：搭建开发环境

在开始编写代码之前，您需要通过在您最喜欢的 IDE 中创建新的 C# 项目来设置开发环境。

## 第 2 步：导入 Aspose.PDF 参考文献

要使用 Aspose.PDF for .NET，您需要向您的项目添加适当的引用。请按照以下步骤导入必要的参考：

1. 在您的项目中，右键单击“引用”并选择“添加引用”。
2. 在“添加引用”窗口中，找到并选择 Aspose.PDF for .NET 的 DLL 文件。
3. 单击“确定”将引用导入到您的项目中。

## 第 3 步：加载 PDF 文件

在提取超链接目标之前，必须将 PDF 文件加载到应用程序中。使用以下代码加载 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载 PDF 文件
Document document = new Document(dataDir + "input.pdf");
```

请务必指定文档目录和要处理的 PDF 文件的正确路径。

## 步骤 4：浏览文档页面

现在 PDF 文件已加载，您需要浏览文档的所有页面。这将使您获得

每个页面上都有超链接注释。使用以下代码遍历文档的页面：

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     //获取特定页面的链接注释
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     //创建一个列表来存储所有链接
     IList<Annotation> list = selector. Selected;
     //循环遍历列表中的每个项目
     foreach(LinkAnnotation a in list)
     {
         //打印目标 URL
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

此代码循环遍历文档的每个页面并选择每个页面上存在的超链接注释。然后它将这些注释存储在列表中并打印每个链接的目标 URL。

## 步骤5：获取超链接目标

最后一步是从超链接注释中提取超链接目的地。以下代码向您展示了如何执行此操作：

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         //根据您的意愿使用目的地
     }
}
```

在此代码中，我们从链接注释中获取每个超链接目标并将目标存储在变量中。然后，您可以根据需要在应用程序中使用该目标。

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
		//获取特定页面的链接注释
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

### 在 PDF 文件中获取超链接目标的常见问题解答

#### 问：PDF 文件中的超链接目标是什么？

答：PDF 文件中的超链接目标是超链接指向的特定位置或目标。它可以是 URL、同一文档中的页面或外部文档。

#### 问：提取超链接目标对我的 PDF 文档分析有何帮助？

答：提取超链接目标允许您识别和编目 PDF 文档中超链接指向的所有目标。此信息可用于内容验证、链接验证和数据分析。

#### 问：Aspose.PDF for .NET 如何协助提取超链接目标？

答：Aspose.PDF for .NET 提供了强大的 API 来轻松提取超链接目标。本教程分步演示如何使用 C# 提取超链接目标。

#### 问：我可以根据特定条件有选择地提取超链接目的地吗？

答：是的，您可以通过迭代 PDF 文档的页面并根据您的条件过滤所需的超链接注释来选择性地提取超链接目标。

#### 问：是否可以从受密码保护的 PDF 文档中提取超链接目标？

答：只要您在打开文档时提供必要的身份验证凭据，Aspose.PDF for .NET 就可以从受密码保护的 PDF 文档中提取超链接目标。

#### 问：如何在我的应用程序中使用提取的超链接目标？

答：提取超链接目标后，您可以使用它们执行各种操作，例如验证链接 URL、创建报告或实施自定义导航。

#### 问：提取超链接目标时有什么限制吗？

答：虽然超链接目标提取功能很强大，但必须考虑 PDF 文档的结构。嵌入复杂图形或多媒体内容中的超链接可能需要额外的处理。

#### 问：我可以提取超链接的其他属性，例如链接类型或坐标吗？

答：本教程重点介绍提取超链接目标。不过，您可以参考 Aspose.PDF 官方文档来探索高级功能，包括提取链接类型和坐标。