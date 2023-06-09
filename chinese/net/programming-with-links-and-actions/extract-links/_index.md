---
title: 提取链接
linktitle: 提取链接
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地从 PDF 文档中提取链接。
type: docs
weight: 50
url: /zh/net/programming-with-links-and-actions/extract-links/
---

从 PDF 文档中提取链接允许您恢复文档中存在的所有超文本链接。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松提取这些链接：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要从中提取链接的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

我们将使用`Document`班级。下面是相应的代码：

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## 第 4 步：提取链接

在此步骤中，我们将使用`AnnotationSelector`班级。下面是相应的代码：

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## 第 5 步：保存更新后的文档

现在让我们使用`Save`的方法`document`目的。下面是相应的代码：

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### 使用 Aspose.PDF for .NET 提取链接的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document document = new Document(dataDir+ "ExtractLinks.pdf");
//提取动作
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
//保存更新的文档
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您现在有了一个使用 Aspose.PDF for .NET 从 PDF 文档中提取链接的分步指南。您可以使用此代码检索文档中存在的所有超链接。

请务必查看官方 Aspose.PDF 文档以获取有关高级链接提取功能的更多信息。