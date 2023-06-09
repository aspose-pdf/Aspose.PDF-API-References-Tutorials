---
title: 创建文档链接
linktitle: 创建文档链接
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松创建指向其他 PDF 文档的链接。
type: docs
weight: 30
url: /zh/net/programming-with-links-and-actions/create-document-link/
---

链接到 PDF 文件中的另一个文档允许您创建可单击的链接，将用户重定向到其他 PDF 文档。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松创建此类链接：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要向其添加指向另一个文档的链接的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在，我们将使用以下代码打开要将链接添加到另一个文档的 PDF 文档：

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## 第 4 步：创建指向另一个文档的链接

在此步骤中，我们将使用`LinkAnnotation`注解。我们将指定链接的坐标和区域，以及指向外部文档的导航操作。下面是相应的代码：

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## 第 5 步：保存更新后的文件

现在让我们使用`Save`的方法`document`目的。下面是相应的代码：

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### 使用 Aspose.PDF for .NET 创建文档链接的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
//创建链接
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
//保存更新的文档
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## 结论

恭喜！您现在有了一个使用 Aspose.PDF for .NET 链接到其他文档的分步指南。您可以使用此代码在 PDF 文件中创建可点击的链接，将用户重定向到其他文档。

请务必查看官方 Aspose.PDF 文档以获取有关交互式链接高级功能的更多信息。