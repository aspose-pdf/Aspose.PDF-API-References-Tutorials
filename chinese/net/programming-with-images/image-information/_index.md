---
title: PDF 文件中的图像信息
linktitle: PDF 文件中的图像信息
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 提取 PDF 文件中的图像信息。
type: docs
weight: 160
url: /zh/net/programming-with-images/image-information/
---
本指南将逐步指导您如何使用 Aspose.PDF for .NET 提取 PDF 文件中的图像信息。确保您已设置环境并按照以下步骤操作：

## 第1步：定义文档目录

确保设置正确的文档目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中添加 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源 PDF 文件

在此步骤中，我们将使用以下命令加载源 PDF 文件`Document` Aspose.PDF 类。使用`Document`构造函数并传递 PDF 文档的路径。

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 步骤 3：设置默认分辨率

在此步骤中，我们将设置图像的默认分辨率。在示例中，默认分辨率设置为 72。

```csharp
int defaultResolution = 72;
```

## 第 4 步：初始化对象和计数器

在此步骤中，我们将初始化检索图像信息所需的对象和计数器。

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## 步骤 5：循环浏览文档首页上的运算符

在此步骤中，我们将遍历文档第一页上的运算符来识别与图像相关的操作。

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## 第6步：管理算子并提取图像信息

在这一步中，我们将管理不同类型的运算符并提取有关图像的信息。

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//处理转换的 GSave 和 GRestore 操作
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
//处理 ConcatenateMatrix 转换操作
else if (opCtm != null)
{
     //应用变换矩阵
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
//处理图像的Do操作
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         //检索图像
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         //检索图像的尺寸
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         //根据以上信息计算分辨率
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         //显示图像信息
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### 使用 Aspose.PDF for .NET 的图像信息示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载源 PDF 文件
Document doc = new Document(dataDir+ "ImageInformation.pdf");
//定义图像的默认分辨率
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
//定义将保存图像名称的数组列表对象
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
//将对象插入堆栈
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
//获取文档第一页上的所有运算符
foreach (Operator op in doc.Pages[1].Contents)
{
	//使用 GSave/GRestore 运算符将转换恢复到先前设置
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	//实例化 ConcatenateMatrix 对象，因为它定义当前变换矩阵。
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	//创建从资源中提取对象的 Do 运算符。它绘制 Form 对象和 Image 对象
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//保存之前的状态并将当前状态推入堆栈顶部
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		//丢弃当前状态并恢复前一个状态
		graphicsState.Pop();
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
		//将当前矩阵与状态矩阵相乘
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		//如果这是一个图像绘制操作员
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			//创建 XImage 对象来保存第一个 pdf 页的图像
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			//获取图像尺寸
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			//获取图像的高度和宽度信息
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			//根据以上信息计算分辨率
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			//显示每张图像的尺寸和分辨率信息
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## 结论

恭喜！您现在已经了解了如何使用 Aspose.PDF for .NET 提取 PDF 文件中的图像信息。您可以将此信息用于应用程序中的各种图像处理任务。

### PDF 文件中图像信息的常见问题解答

#### 问：使用 Aspose.PDF for .NET 从 PDF 文档中提取图像信息的目的是什么？

答：从 PDF 文档中提取图像信息可以深入了解文档中图像的尺寸、分辨率和其他属性。该信息可用于图像处理、分析或优化任务。

#### 问：Aspose.PDF for .NET 如何协助从 PDF 文档中提取图像信息？

答：Aspose.PDF for .NET 提供了访问和分析 PDF 文档内容（包括图像）的工具。提供的代码演示了如何使用各种运算符提取和显示图像信息。

#### 问：该方法可以提取哪些图像信息？

答：此方法允许您提取并显示 PDF 文档中图像的信息，例如缩放尺寸、分辨率和图像名称。

#### 问：代码如何识别和处理 PDF 文档中与图像相关的运算符？

答：代码会迭代 PDF 文档指定页面上的运算符。它识别并处理与图像操作、转换和渲染相关的运算符。

#### 问：默认解析的意义是什么，在代码中是如何使用的？

A：以默认分辨率为参考点来计算图像的实际分辨率。该代码根据每个图像的尺寸和默认分辨率设置计算其分辨率。

#### 问：提取的图像信息如何应用于现实场景？

答：提取的图像信息可用于图像质量评估、图像优化、生成图像缩略图以及促进图像相关决策过程等任务。

#### 问：我可以修改代码来提取其他与图像相关的属性吗？

答：是的，您可以自定义代码来提取图像的其他属性，例如色彩空间、像素深度或图像类型。

#### 问：图像信息提取过程是否占用资源或耗时？

答：图像信息提取过程高效且针对性能进行了优化，确保对资源使用和处理时间的影响最小。

#### 问：开发人员如何从 PDF 文档中识别和提取图像信息中受益？

答：开发人员可以深入了解 PDF 文档中图像的特征，使他们能够就图像操作、处理和优化做出明智的决策。

#### 问：该方法可以用于批量处理包含图像的PDF文档吗？

答：是的，该方法可以通过迭代多个页面或文档、提取图像信息以及执行与图像相关的任务来扩展批处理。