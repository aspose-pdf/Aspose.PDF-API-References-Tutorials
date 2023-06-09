---
title: 添加透明文本
linktitle: 添加透明文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将透明文本添加到 PDF 文档。
type: docs
weight: 100
url: /zh/net/programming-with-text/add-transparent-text/
---

本教程将指导您完成使用 Aspose.PDF for .NET 向 PDF 文档添加透明文本的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具有以下内容：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- .NET 库的 Aspose.PDF。您可以从 Aspose 官方网站下载它，或者使用像 NuGet 这样的包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入所需的命名空间
在要添加透明文本的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## 第三步：设置文档目录
在代码中，找到显示的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并更换`"YOUR DOCUMENT DIRECTORY"`与存储文档的目录的路径。

## 第 4 步：创建一个新的 Document 实例
实例化一个新的`Document`通过添加以下代码行对象：

```csharp
Document doc = new Document();
```

## 第 5 步：向文档添加页面
通过使用向文档添加新页面`Add`的方法`Pages`收藏。在提供的代码中，新页面被分配给变量`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 6 步：创建一个 Graph 对象
创建一个新的`Graph`具有特定宽度和高度的对象。

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## 第 7 步：创建一个具有透明度的矩形
创建一个具有特定尺寸的矩形，并使用`Color.FromRgb`方法。

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## 第 8 步：将 Graph 对象添加到页面
添加`Graph`反对页面的段落集合。

```csharp
page.Paragraphs.Add(canvas);
```

## 第 9 步：设置图形对象的位置
设置`IsChangePosition`的财产`Graph`反对`false`以防止它改变位置。

```csharp
canvas. IsChangePosition = false;
```

## 第 10 步：创建具有透明度的 TextFragment
创建一个`TextFragment`对象并将其内容设置为所需的文本。设置`ForegroundColor`的财产`TextState`使用具有透明度的颜色`Color.FromArgb`方法。

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## 步骤 11：保存 PDF 文档
使用保存 PDF 文档`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 添加透明文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建文档实例
Document doc = new Document();
//创建页面到页面集合的 PDF 文件
Aspose.Pdf.Page page = doc.Pages.Add();
//创建图形对象
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//创建具有特定尺寸的矩形实例
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
//从 Alpha 颜色通道创建颜色对象
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
//将矩形添加到 Graph 对象的形状集合
canvas.Shapes.Add(rect);
//将图形对象添加到页面对象的段落集合
page.Paragraphs.Add(canvas);
//将值设置为不更改图形对象的位置
canvas.IsChangePosition = false;
//使用示例值创建 TextFragment 实例
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
//从 Alpha 通道创建颜色对象
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
//为文本实例设置颜色信息
text.TextState.ForegroundColor = color;
//将文本添加到页面实例的段落集合
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## 结论
您已经使用 Aspose.PDF for .NET 成功地将透明文本添加到您的 PDF 文档。现在可以在指定的输出文件路径中找到生成的 PDF 文件。