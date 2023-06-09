---
title: 添加超链接
linktitle: 添加超链接
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在您的 PDF 文件中轻松添加交互式超链接。
type: docs
weight: 10
url: /zh/net/programming-with-links-and-actions/add-hyperlink/
---

在 PDF 文档中添加超链接允许您创建指向文档中其他页面、网站或目标的交互式超链接。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松添加超链接：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要添加超链接的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在我们将使用以下代码打开我们要添加超链接的 PDF 文档：

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## 第 4 步：创建链接

在此步骤中，我们将使用`LinkAnnotation`注解。我们会注明联系方式和链接区域、链接类型和链接内容。下面是相应的代码：

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## 第 5 步：添加其他文本

除了超链接，我们还可以使用`FreeTextAnnotation`注解。我们将指定坐标、文本外观和文本内容。下面是相应的代码：

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## 第 6 步：保存更新后的文件

现在让我们使用`Save`的方法`document`目的。下面是相应的代码：

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### 使用 Aspose.PDF for .NET 添加超链接的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document document = new Document(dataDir + "AddHyperlink.pdf");
//创建链接
Page page = document.Pages[1];
//创建链接注释对象
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
//为 LinkAnnotation 创建边框对象
Border border = new Border(link);
//设置边框宽度值为 0
border.Width = 0;
//为 LinkAnnotation 设置边框
link.Border = border;
//将链接类型指定为远程 URI
link.Action = new GoToURIAction("www.aspose.com");
//将链接注释添加到PDF文件第一页的注释集合
page.Annotations.Add(link);
//创建自由文本注释
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
//要作为自由文本添加的字符串
textAnnotation.Contents = "Link to Aspose website";
//为自由文本注释设置边框
textAnnotation.Border = border;
//将 FreeText 注释添加到 Document 第一页的注释集合
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
//保存更新的文档
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## 结论

恭喜！您现在有了使用 Aspose.PDF for .NET 添加超链接的分步指南。您可以使用此代码在 PDF 文档中创建交互式链接。