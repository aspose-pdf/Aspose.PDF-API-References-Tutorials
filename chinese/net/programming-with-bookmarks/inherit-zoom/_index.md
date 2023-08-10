---
title: 继承放大 PDF 文件
linktitle: 继承放大 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松继承 PDF 文件中的书签缩放。
type: docs
weight: 90
url: /zh/net/programming-with-bookmarks/inherit-zoom/
---
PDF 文件中的缩放继承允许您指定书签的默认缩放级别。使用Aspose.PDF for .NET，您可以通过以下源代码轻松继承缩放：

## 第1步：导入所需的库

在开始之前，您需要为 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 步骤 2：设置文档文件夹路径

在此步骤中，您需要指定包含要继承缩放的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 3：打开 PDF 文档

现在我们将使用以下代码打开要继承缩放的 PDF 文档：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第四步：获取书签集合

在此步骤中，我们将使用以下方法获取文档的书签或地标的集合`Outlines`的财产`doc`目的。这是相应的代码：

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## 第 5 步：设置缩放级别

现在我们将通过创建一个来设置缩放级别`XYZExplicitDestination`具有指定 x、y 和 z 坐标的对象。这里我们使用坐标(100, 100, 0)，缩放为2。下面是相应的代码：

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## 第 6 步：将缩放级别添加到书签

在此步骤中，我们添加`XYZExplicitDestination`对象作为对书签的操作`item`收藏。这是相应的代码：

```csharp
item. Action = new GoToAction(dest);
```

## 步骤 7：将更新后的书签添加到文档中

最后，我们使用以下命令将更新后的书签添加到文档的书签集合中：`Add`的方法`doc.Outlines`目的。这是相应的代码：

```csharp
doc. Outlines. Add(item);
```

## 第 8 步：保存更新的文件

现在让我们使用以下命令保存更新后的 PDF 文件`Save`的方法`doc`目的。这是相应的代码：

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 继承缩放的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document doc = new Document(dataDir + "input.pdf");
//获取PDF文件的大纲/书签集合
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
//将缩放级别设置为 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
//添加 XYZExplicitDestination 作为操作来概述 PDF 集合
item.Action = new GoToAction(dest);
//将项目添加到 PDF 文件的大纲集合
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
//保存输出
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！现在您有了使用 Aspose.PDF for .NET 继承 Zoom 的分步指南。您可以使用此代码指定 PDF 文档中书签的默认缩放级别。

请务必查看官方 Aspose.PDF 文档，以获取有关高级书签操作功能的更多信息。

### PDF 文件继承缩放的常见问题解答

#### 问：什么是 PDF 文件中的缩放继承？

答：缩放继承是指为 PDF 文档中的书签指定默认缩放级别的功能。当用户与书签交互时，这可以实现一致且用户友好的导航。

#### 问：为什么我要继承书签的缩放级别？

答：继承缩放级别可确保用户在浏览 PDF 文档中的书签时获得一致的查看体验。当您想要为文档的不同部分提供特定视图时，它会特别有用。

#### 问：如何导入 C# 项目所需的库？

答：要导入 C# 项目所需的库，请包含以下导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

这些指令使您能够访问处理 PDF 文档和书签所需的类和方法。

#### 问：如何指定文档文件夹的路径？

 A：在提供的源代码中，替换`"YOUR DOCUMENT DIRECTORY"`包含要继承缩放级别的 PDF 文件的文件夹的实际路径。

#### 问：如何打开 PDF 文档以继承缩放级别？

答：要打开 PDF 文档以继承缩放级别，请使用以下代码：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

代替`"input.pdf"`与实际的文件名。

#### 问：如何设置书签的缩放级别？

 A：要设置缩放级别，请创建一个`XYZExplicitDestination`具有所需坐标和缩放系数的对象。这是一个例子：

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

这会将坐标 (100, 100) 处的缩放级别设置为 2。

#### 问：如何将缩放级别添加到书签？

答：添加`XYZExplicitDestination`对象作为书签集合的操作：

```csharp
item.Action = new GoToAction(dest);
```

在哪里`item`是一个`OutlineItemCollection`代表一个书签。

#### 问：如何保存更新后的 PDF 文件？

答：使用以下命令保存更新的 PDF 文件`Save`的方法`doc`目的：

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### 问：我可以为不同的书签自定义缩放级别吗？

答：是的，您可以通过创建多个书签来自定义不同书签的缩放级别`XYZExplicitDestination`具有不同坐标和缩放系数的对象。

#### 问：我可以应用缩放继承的书签数量有限制吗？

答：通常，您可以应用缩放继承的书签数量没有严格限制。然而，具有过多书签的非常大的文档可能需要高效的内存管理。

#### 问：如何确认缩放继承已应用？

答：打开生成的 PDF 文件以验证书签是否继承了指定的缩放级别。