---
title: 提取PDF文件中的边框
linktitle: 提取PDF文件中的边框
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 提取 PDF 文件中的边框。
type: docs
weight: 80
url: /zh/net/programming-with-tables/extract-border/
---
在本教程中，我们将学习如何使用 Aspose.PDF for .NET 提取 PDF 文件中的边框。我们将逐步解释 C# 中的源代码。在本教程结束时，您将了解如何从 PDF 文档中提取边框并将其保存为图像。让我们开始吧！

## 步骤 1：设置环境
首先，确保您已使用 Aspose.PDF for .NET 设置了 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 步骤 2：加载 PDF 文档
在此步骤中，我们从指定的文件加载 PDF 文档。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

请确保将“您的文档目录”替换为您的 PDF 文件所在的实际目录。

## 步骤3：边缘提取
我们将通过迭代文档中包含的操作从 PDF 文档中提取边框。

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     //处理所有内容操作
     foreach(Operator op in doc.Pages[1].Contents)
     {
         //检查操作类型
         // ...
         //添加代码来处理每个操作
     }
}
```

我们创建`graphicsState`堆栈来存储图形状态，位图图像来捕获提取的边框，`GraphicsPath`对象来存储绘图路径，以及其他变量来跟踪状态和颜色。

## 步骤4：交易处理
在这一步中，我们处理文档的每个操作来提取边框。

```csharp
//检查操作类型
if (opSaveState != null)
{
     //保存先前的状态，并将当前状态推送到堆栈顶部
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     //删除当前状态并恢复之前的状态
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     //检索当前变换矩阵
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     //将当前矩阵与状态矩阵相乘
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     //更新最后一个绘制点
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     //处理线条的绘制
     // ...
     //添加代码来处理绘制线条
}
// ...
//为其他操作添加 else if 块
```

我们使用条件检查操作的类型并为每个操作运行适当的代码。

## 步骤 5：备份图像
最后，我们将包含提取边框的位图图像保存到指定的文件中。

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

确保指定正确的目录和文件名来保存输出图像。

### 使用 Aspose.PDF for .NET 提取边框的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
//默认 ctm 矩阵值为 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.Drawing 坐标系基于左上角，而 pdf 坐标系基于左下角，因此我们必须应用反转矩阵
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	//处理所有内容命令
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//保存先前的状态并将当前状态推送到堆栈顶部
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			//丢弃当前状态并恢复先前状态
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opCtm != null)
		{
			System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
				(float)opCtm.Matrix.A,
				(float)opCtm.Matrix.B,
				(float)opCtm.Matrix.C,
				(float)opCtm.Matrix.D,
				(float)opCtm.Matrix.E,
				(float)opCtm.Matrix.F);

			//将电流矩阵与状态矩阵相乘
			((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
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
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 从 PDF 文档中提取边框。您可以使用本分步指南从其他 PDF 文档中提取边框。

### PDF 文件中边框提取常见问题

#### 问：从 PDF 文件中提取边框有什么用？

答：从 PDF 文件中提取边框可用于多种用途。它允许您隔离和分析文档的结构元素，例如表格、图表或图形元素。您可以使用提取的边框来识别 PDF 文档中内容的布局、尺寸和定位。

#### 问：我可以从 PDF 文档内的特定页面或区域提取边框吗？

答：是的，您可以修改提供的 C# 源代码，从 PDF 文档中的特定页面或区域提取边框。通过操作`doc.Pages`收集并指定自定义标准，您可以选择从特定页面或感兴趣的区域提取边框。

#### 问：如何自定义输出图像格式和质量？

答：在提供的 C# 代码中，提取的边框保存为 PNG 图像。如果要更改输出图像格式，可以修改`ImageFormat.Png`参数`bitmap.Save`方法转换为其他受支持的图像格式，例如 JPEG、BMP 或 GIF。此外，您可以根据需要调整图像质量或压缩设置。

#### 问：提取出的边框还能进行哪些操作？

答：将边框提取为图像后，您可以使用图像处理库或算法对其进行进一步处理。您可以分析图像、应用图像过滤器、检测图案，或执行 OCR（光学字符识别）以从图像中提取文本（如果需要）。

#### 问：从复杂的 PDF 文档中提取边框时有什么限制或注意事项吗？

答：提取过程可能因 PDF 文档的复杂程度而异。具有多层、透明度或高级图形的复杂 PDF 可能需要额外的处理或调整才能准确提取边框。对各种 PDF 文档进行彻底测试提取过程以确保结果可靠至关重要。