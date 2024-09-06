---
title: 查看时指定页面
linktitle: 查看时指定页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何在使用 Aspose.PDF for .NET 查看 PDF 时指定页面。
type: docs
weight: 110
url: /zh/net/programming-with-links-and-actions/specify-page-when-viewing/
---
通过本分步指南了解如何在使用 Aspose.PDF for .NET 查看 PDF 文件时指定页面。

## 步骤 1：设置环境

确保您已经使用 C# 项目和适当的 Aspose.PDF 参考设置了开发环境。

## 步骤 2：加载 PDF 文件

设置文档的目录路径并使用以下代码上传 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载 PDF 文件
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## 步骤 3：指定目标页面

使用以下代码获取目标页面实例：

```csharp
Page page2 = doc.Pages[2];
```

您可以调整索引`[2]`选择所需的页面。

## 步骤 4：配置缩放设置

创建一个变量来设置目标页面缩放系数：

```csharp
double zoom = 1;
```

您可以根据需要调整缩放值。

## 步骤 5：创建导航操作

使用指定的目标页面创建导航操作的实例：

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## 步骤 6：设置目的地

使用坐标和缩放设置前往目标页面的目的地：

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## 步骤 7：配置文档打开操作

使用创建的导航操作设置文档打开操作：

```csharp
doc. OpenAction = action;
```

## 步骤 8：保存更新的文档

使用保存更新的文档`Save`方法：

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
//创建变量来设置目标页面的缩放系数
double zoom = 1;
//创建 GoToAction 实例
GoToAction action = new GoToAction(doc.Pages[2]);
//转至第 2 页
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
//设置文档打开操作
doc.OpenAction = action;
//保存更新的文档
doc.Save(dataDir + "goto2page_out.pdf");
```

## 结论

恭喜！您现在知道如何在使用 Aspose.PDF for .NET 查看 PDF 时指定页面。利用这些知识来自定义 PDF 文档中的用户查看体验。

现在您已经完成本指南，您可以将这些概念应用到您自己的项目中，并进一步探索 Aspose.PDF for .NET 提供的功能。

### 常见问题解答 

#### 问：查看 PDF 文件时指定目标页面有什么用？

答：指定目标页面允许您控制打开文件时显示 PDF 文档的哪一页。这可以通过将用户引导至感兴趣的特定页面来增强用户体验。

#### 问：在 PDF 文档中指定目标页面有何用处？

答：当您想要引导用户访问 PDF 文档中的特定部分或内容，而无需他们手动浏览各个页面时，指定目标页面会很有用。

#### 问：Aspose.PDF for .NET 如何帮助指定要查看的目标页面？

答：Aspose.PDF for .NET 提供的 API 允许您设置 PDF 文档的初始视图，包括目标页面、缩放级别和其他显示属性。

#### 问：我可以指定任意页面作为目标页面吗？

答：是的，您可以指定 PDF 文档中的任意页面作为查看的目标页面。只需使用相应的索引选择所需的页面即可。

#### 问：指定目标页面时缩放比例有什么意义？

答：缩放系数决定了打开 PDF 文档时对目标页面应用的放大级别。它控制视口内显示的内容量。

#### 问：我可以为不同的目标页面设置不同的缩放比例吗？

答：是的，您可以通过创建单独的页面为不同的目标页面设置不同的缩放比例。`GoToAction`实例并相应地配置它们的目的地。

#### 问：指定目标页面有什么限制吗？

答：指定目标页面仅限于控制 PDF 打开时的初始视图。它不会影响 PDF 显示后的用户交互或导航。

#### 问：我可以使用此功能在 PDF 文档中创建演示文稿吗？

答：是的，您可以使用此功能在 PDF 文档中创建类似演示的体验，引导用户浏览不同的部分或主题。

#### 问：我可以自定义初始视图的其他方面，例如页面布局吗？

答：是的，Aspose.PDF for .NET 提供了自定义初始视图其他方面的属性，包括页面布局、页面模式等。

#### 问：如何测试指定的目标页面和缩放比例是否按预期工作？

答：应用提供的代码指定目标页面和缩放比例后，打开修改后的 PDF 文件并验证它是否以正确的页面和缩放级别打开。