---
title: 添加 Swf 文件作为注释
linktitle: 添加 Swf 文件作为注释
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何在 Aspose.PDF for .NET 中将 SWF 文件添加为注释。
type: docs
weight: 30
url: /zh/net/annotations/addswffileasannotation/
---
如果您是 .NET 开发人员，希望使用 Aspose.PDF for .NET 将 SWF 多媒体文件作为注释添加到您的 PDF 文档中，那么本分步指南适合您。在本文中，我们将解释如何使用 C# 编程语言将 SWF 文件添加为 PDF 文档中的注释。 

按照以下步骤使用 Aspose.PDF for .NET 在您的 PDF 文档中添加一个 SWF 文件作为注释：

## 第一步：设置目录路径

首先，我们需要设置PDF文件和SWF文件的存放目录路径。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

将“您的文档目录”替换为您的文档目录的路径。

## 第 2 步：加载 PDF 文档

接下来，我们需要使用以下代码加载 PDF 文档：

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

此代码将从文档目录加载“AddSwfFileAsAnnotation.pdf”文件。

## 第三步：获取添加注解的页面

现在，我们需要获取要添加注释的页面的引用。在本教程中，我们将注释添加到文档的第一页。

```csharp
Page page = doc.Pages[1];
```

## 第 4 步：创建 ScreenAnnotation 对象

我们现在可以创建一个`ScreenAnnotation`以 SWF 文件作为参数的对象。

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

这`ScreenAnnotation`构造函数接受三个参数：

- `page`: 将添加注释的页面。
- `rectangle`：SWF 文件将在页面上显示的矩形。
- `dataDir + "input.swf"`：SWF 文件的路径。

## 第五步：给页面添加注解

现在，我们可以将注释添加到页面的注释集合中。

```csharp
page.Annotations.Add(annotation);
```

## 步骤 6：保存更新后的 PDF 文档

最后，我们需要使用以下代码保存更新后的带有注释的 PDF 文档：

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

此代码将更新的 PDF 文档与注释保存为文档目录中的“AddSwfFileAsAnnotation_out.pdf”。

### 使用 Aspose.PDF for .NET 添加 SWF 文件作为注释的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

//获取需要添加注释的页面的引用
Page page = doc.Pages[1];

//使用 .swf 多媒体文件作为参数创建 ScreenAnnotation 对象
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

//添加注释到页面的注释集合
page.Annotations.Add(annotation);

dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
//保存带有注释的更新 PDF 文档
doc.Save(dataDir);
```        
