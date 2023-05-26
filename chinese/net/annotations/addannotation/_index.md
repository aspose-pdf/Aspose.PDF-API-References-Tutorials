---
title: 添加注释
linktitle: 添加注释
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用此 C# 源代码使用 Aspose.PDF for .NET 添加文本注释。使用特定的细节和图标自定义您的注释。
type: docs
weight: 10
url: /zh/net/annotations/addannotation/
---

向 PDF 文档添加注释是一项强大的功能，可以增强协作和审阅流程。 Aspose.PDF for .NET 使使用 C# 以编程方式向 PDF 文档添加注释变得容易。在本指南中，我们将逐步解释如何使用 Aspose.PDF for .NET 为 PDF 文档添加注释。

## 第 1 步：创建一个新项目并安装 Aspose.PDF for .NET

在我们开始编写添加注释的代码之前，我们需要创建一个新项目并安装 Aspose.PDF for .NET。要为 .NET 安装 Aspose.PDF，请执行以下步骤：

1. 打开 Visual Studio 并创建一个新的 C# 项目。
2. 右键单击解决方案资源管理器中的项目，然后选择“管理 NuGet 包”。
3. 搜索“Aspose.PDF”并选择“安装”。

安装完成后，我们就可以开始编写代码了。

## 第 2 步：打开 PDF 文档

添加注释的第一步是打开 PDF 文档。我们可以使用下面的代码打开文档：

```
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

在此代码中，我们指定要打开的 PDF 文档的路径。确保将“您的数据目录”替换为数据目录的实际路径。

## 第 3 步：创建注释

要添加注释，我们需要创建一个新的实例`TextAnnotation`班级。我们可以使用下面的代码来创建一个新的文本注释：

```
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

在这段代码中，我们在 PDF 文档的第二页上创建了一个新的文本注释。我们还设置了注释的标题、主题、状态、内容、打开和图标属性。

## 第 4 步：自定义注释

我们可以使用自定义注释的外观`Border`班级。我们可以使用下面的代码来自定义注解的边框：

```
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

在这段代码中，我们创建了一个新的`Border`对象并设置其宽度和破折号属性。然后我们设置`Border`新注释的属性`Border`目的。最后，我们设置`Rect`注释的属性来指定它的位置和大小。

## 第 5 步：将批注添加到 PDF 文档

创建并自定义注释后，我们需要将其添加到 PDF 文档中。我们可以使用下面的代码给PDF文档添加注释：

```
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

在这段代码中，我们将注释添加到 PDF 文档第二页的注释集合中。

## 第 6 步：保存输出文件

最后，我们需要保存添加了注释的 PDF 文档。我们可以使用以下代码来保存输出文件：

```
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### 使用 Aspose.PDF for .NET 添加注释的示例源代码


```csharp   
	 //文档目录的路径。
	string dataDir = "YOUR DATA DIRECTORY";

	//打开文档
	Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

	//创建注释
	TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
	textAnnotation.Title = "Sample Annotation Title";
	textAnnotation.Subject = "Sample Subject";
	textAnnotation.State = AnnotationState.Accepted;
	textAnnotation.Contents = "Sample contents for the annotation";
	textAnnotation.Open = true;
	textAnnotation.Icon = TextIcon.Key;
   
	Border border = new Border(textAnnotation);
	border.Width = 5;
	border.Dash = new Dash(1, 1);
	textAnnotation.Border = border;
	textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
   
	//在页面的注解集合中添加注解
	pdfDocument.Pages[1].Annotations.Add(textAnnotation);
	dataDir = dataDir + "AddAnnotation_out.pdf";
	//保存输出文件
	pdfDocument.Save(dataDir);
```
此代码演示了如何使用 Aspose.PDF for .NET 将具有特定标题、主题、状态、内容和图标的文本注释添加到 PDF 页面。您可以根据您的要求修改此代码，以便为您的 PDF 文档添加注释。请记住将您的数据目录替换为您的 PDF 文件所在的实际目录路径以及您要保存输出文件的位置。