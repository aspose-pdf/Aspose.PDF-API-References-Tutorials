---
title: 提取PDF文件中的边框
linktitle: 提取PDF文件中的边框
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文件中提取边框并将其保存为图像。带有代码示例和成功秘诀的分步指南。
type: docs
weight: 80
url: /zh/net/programming-with-tables/extract-border/
---
## 介绍

处理 PDF 时，提取边框或图形路径等特定元素似乎是一项艰巨的任务。但使用 Aspose.PDF for .NET，您可以轻松地从 PDF 文件中提取边框或形状并将其保存为图像。在本教程中，我们将深入研究从 PDF 中提取边框并将其保存为 PNG 图像的过程。准备好控制 PDF 的图形内容吧！

## 先决条件

在深入研究代码之前，请确保已完成所有设置：

1.  Aspose.PDF for .NET：如果您尚未安装 Aspose.PDF 库，您可以[点击下载](https://releases.aspose.com/pdf/net/)。您还需要通过免费试用版或购买许可证来申请许可证。
2. IDE 设置：在 Visual Studio 或任何其他 .NET IDE 中设置 C# 项目。确保已添加对 Aspose.PDF 库的必要引用。
3. 输入 PDF 文件：准备好一个 PDF 文件，您将从中提取边框。本教程将引用名为`input.pdf`.

## 导入所需包

让我们从导入所需的命名空间开始。这些包提供了操作 PDF 内容所需的工具。

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

现在我们已经了解了基础知识，让我们进入分步指南，我们将分解代码的每个部分以详细解释它。


## 步骤 1：加载 PDF 文档

第一步是加载包含要提取边框的 PDF 文档。就像在开始阅读之前打开一本书一样 — 您需要访问内容！

我们首先指定 PDF 文件的存储目录，然后使用`Aspose.Pdf.Document`班级。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

此代码加载`input.pdf`从您指定的目录中获取文件。确保文件路径正确，否则您可能会收到文件未找到错误。

## 步骤 2：设置图形和位图

在开始提取之前，我们需要创建一个画布来绘制。在 .NET 世界中，这意味着设置 Bitmap 和 Graphics 对象。Bitmap 代表图像，Graphics 对象允许我们绘制从 PDF 中提取的形状，例如边框。

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

具体如下：
- 我们创建一个与 PDF 第一页大小相同的位图图像。
- GraphicsPath 用于定义形状（在本例中为边框）。
- 矩阵定义了图形如何转换；我们需要一个反转矩阵，因为 PDF 和 .NET 有不同的坐标系。

## 步骤3：处理PDF内容


PDF文件是一系列的绘图命令，我们需要对这些命令逐一进行处理，识别并提取边框信息。

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    //处理保存/恢复状态、绘制线条、填充形状等命令。
}
```

代码循环遍历 PDF 内容流中的每个绘图操作符。每个操作符可能代表一条线、一个矩形或其他图形指令。

## 步骤 4：处理 PDF 运算符

PDF 文件中的每个运算符都控制一个操作。要提取边框，我们需要识别诸如“移动到”、“线到”和“绘制矩形”之类的命令。以下运算符处理这些操作：

- MoveTo：将光标移动到起点。
- LineTo：从当前点到新点画一条线。
- 回复：绘制一个矩形（这可能是边框的一部分）。

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

在此步骤中：
- 我们捕捉所画的每条线或形状的点。
- 对于矩形（`opRe` ），我们直接将它们添加到`graphicsPath`，我们稍后会使用它来绘制边框。

## 第五步：画出边框

一旦我们确定了构成边框的线条和矩形，我们就需要将它们实际绘制到 Bitmap 对象上。这就是 Graphics 对象的用武之地。

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- 我们根据位图创建一个 Graphics 对象。
- SmoothingMode.HighQuality 确保我们获得漂亮流畅的图像。
- 最后我们使用DrawPath来绘制边框。

## 步骤6：保存提取的边框

现在我们已经提取了边框，是时候将其保存为图像文件了。这会将边框保存为 PNG。

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- 位图保存为 PNG 图像。
- 您现在可以打开此图像来查看提取的边框。

## 结论

使用 Aspose.PDF for .NET 从 PDF 文件中提取边框乍一看似乎有些棘手，但一旦分解，就会变得简单。通过了解 PDF 中的绘图运算符并利用强大的 .NET 库，您可以高效地操作和提取图形内容。本指南为您提供了开始进行 PDF 操作的坚实基础！

## 常见问题解答

### 如何处理 PDF 中的多页？  
您可以通过迭代来循环遍历文档中的每一页`doc.Pages`而不是硬编码`doc.Pages[1]`.

### 我可以使用相同的方法提取其他元素（例如文本）吗？  
是的，Aspose.PDF 提供了丰富的 API 来从 PDF 文件中提取文本、图像和其他内容。

### 我如何申请许可证以避免限制？  
你可以[申请执照](https://purchase.aspose.com/temporary-license/)通过加载`License`Aspose 提供的类。

### 如果我的 PDF 没有边框怎么办？  
如果您的 PDF 不包含可见边框，则图形提取过程可能不会产生任何结果。请确保 PDF 内容包含可绘制边框。

### 我可以将输出保存为 PNG 以外的格式吗？  
是的，只需更改`ImageFormat.Png`转换为其他受支持的格式，例如`ImageFormat.Jpeg`.