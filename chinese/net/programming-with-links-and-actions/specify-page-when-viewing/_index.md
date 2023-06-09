---
title: 查看时指定页面
linktitle: 查看时指定页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 查看 PDF 时指定页面。
type: docs
weight: 110
url: /zh/net/programming-with-links-and-actions/specify-page-when-viewing/
---

通过此分步指南了解如何在使用 Aspose.PDF for .NET 查看 PDF 文件时指定页面。

## 第 1 步：设置环境

确保您已经使用 C# 项目和适当的 Aspose.PDF 参考设置了您的开发环境。

## 第 2 步：加载 PDF 文件

使用以下代码设置文档的目录路径并上传 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载 PDF 文件
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## 第三步：指定目标页面

使用以下代码获取目标页面实例：

```csharp
Page page2 = doc.Pages[2];
```

你可以调整指数`[2]`选择所需的页面。

## 第 4 步：配置缩放设置

创建一个变量来设置目标页面缩放系数：

```csharp
double zoom = 1;
```

您可以根据需要调整缩放值。

## 第 5 步：创建导航操作

使用指定的目标页面创建导航操作的实例：

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## 第 6 步：设置目的地

使用坐标和缩放设置目的地以转到目标页面：

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## 步骤 7：配置文档打开操作

使用创建的导航操作设置文档打开操作：

```csharp
doc. OpenAction = action;
```

## 步骤 8：保存更新的文档

使用`Save`方法：

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### 使用 Aspose.PDF for .NET 查看时指定页面的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载 PDF 文件
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
//获取文档第二页的实例
Page page2 = doc.Pages[2];
//创建变量以设置目标页面的缩放系数
double zoom = 1;
//创建 GoToAction 实例
GoToAction action = new GoToAction(doc.Pages[2]);
//转到第 2 页
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
//设置文档打开动作
doc.OpenAction = action;
//保存更新的文档
doc.Save(dataDir + "goto2page_out.pdf");
```

## 结论

恭喜！您现在知道如何使用 Aspose.PDF for .NET 查看 PDF 时指定页面。使用这些知识来自定义 PDF 文档中的用户查看体验。

现在您已经完成了本指南，您可以将这些概念应用到您自己的项目中并进一步探索 Aspose.PDF for .NET 提供的功能。