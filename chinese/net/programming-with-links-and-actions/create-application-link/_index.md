---
title: 创建应用程序链接
linktitle: 创建应用程序链接
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在您的 PDF 文件中轻松创建应用程序链接。
type: docs
weight: 20
url: /zh/net/programming-with-links-and-actions/create-application-link/
---

在 PDF 文档中创建应用程序链接允许您创建指向外部应用程序的链接，例如可执行文件或 URL。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松创建应用程序链接：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定要添加应用程序链接的 PDF 文件所在文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在我们将使用以下代码打开我们要添加应用程序链接的 PDF 文档：

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## 第 4 步：创建应用程序链接

在此步骤中，我们将使用`LinkAnnotation`注解。我们将指定链接的坐标和区域，以及应用程序启动操作。下面是相应的代码：

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## 第 5 步：保存更新后的文件

现在让我们使用`Save`的方法`document`目的。下面是相应的代码：

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### 使用 Aspose.PDF for .NET 创建应用程序链接的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
//创建链接
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
//保存更新的文档
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您现在有了使用 Aspose.PDF for .NET 创建应用程序链接的分步指南。您可以使用此代码在 PDF 文档中添加指向外部应用程序的链接。

请务必查看官方 Aspose.PDF 文档以获取有关交互式链接高级功能的更多信息。