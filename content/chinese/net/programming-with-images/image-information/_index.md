---
title: PDF文件中的图像信息
linktitle: PDF文件中的图像信息
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 提取 PDF 文件中的图像信息。
type: docs
weight: 160
url: /zh/net/programming-with-images/image-information/
---
本指南将逐步指导您如何使用 Aspose.PDF for .NET 提取 PDF 文件中图像的信息。确保您已设置环境并按照以下步骤操作：

## 步骤1：定义文档目录

确保设置正确的文档目录。替换`"YOUR DOCUMENT DIRECTORY"`在代码中添加 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源 PDF 文件

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 步骤 3：设置默认分辨率

在此步骤中，我们将设置图像的默认分辨率。在示例中，默认分辨率设置为 72。

```csharp
int defaultResolution = 72;
```

## 步骤 4：初始化对象和计数器

在此步骤中，我们将初始化检索图像信息所需的对象和计数器。

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## 步骤 5：循环浏览文档第一页上的运算符

在此步骤中，我们将遍历文档第一页上的操作符来识别与图像相关的操作。

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## 步骤6：管理操作员并提取图像信息

在这一步中，我们将管理不同类型的操作员并提取有关图像的信息。

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
//处理转换的 ConcatenateMatrix 操作
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
//处理图像的 Do 操作
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
//定义保存图像名称的数组列表对象
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
//将对象插入堆栈
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
//获取文档第一页上的所有操作符
foreach (Operator op in doc.Pages[1].Contents)
{
	//使用 GSave/GRestore 操作符将转换恢复到之前设置的状态
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	//实例化 ConcatenateMatrix 对象，因为它定义当前转换矩阵。
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	//创建从资源中绘制对象的 Do 操作符。它绘制 Form 对象和 Image 对象
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//保存先前的状态并将当前状态推送到堆栈顶部
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		//丢弃当前状态并恢复先前状态
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
		//将电流矩阵与状态矩阵相乘
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		//如果这是图像绘制运算符
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
			//显示每幅图像的尺寸和分辨率信息
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## 结论

恭喜！您现在已经学会了如何使用 Aspose.PDF for .NET 提取 PDF 文件中的图像信息。您可以在应用程序中使用此信息执行各种图像处理任务。

### PDF 文件中图像信息的常见问题解答

#### 问：使用 Aspose.PDF for .NET 从 PDF 文档中提取图像信息的目的是什么？

答：从 PDF 文档中提取图像信息可以深入了解文档中图像的尺寸、分辨率和其他属性。这些信息可用于图像处理、分析或优化任务。

#### 问：Aspose.PDF for .NET 如何帮助从 PDF 文档中提取图像信息？

答：Aspose.PDF for .NET 提供了访问和分析 PDF 文档内容（包括其图像）的工具。提供的代码演示了如何使用各种运算符提取和显示图像信息。

#### 问：用这种方法可以提取什么样的图像信息？

答：此方法允许您提取和显示 PDF 文档中图像的缩放尺寸、分辨率和图像名称等信息。

#### 问：代码如何识别和处理PDF文档中与图像相关的操作符？

答：代码会遍历 PDF 文档中指定页面上的运算符。它会识别并处理与图像操作、转换和渲染相关的运算符。

#### Q：默认解析有什么意义，在代码中如何使用？

答：默认分辨率是作为计算图像实际分辨率的参考点。代码根据图像尺寸和默认分辨率设置计算每幅图像的分辨率。

#### 问：提取的图像信息如何运用到实际场景中？

答：提取的图像信息可用于图像质量评估、图像优化、生成图像缩略图以及促进与图像相关的决策过程等任务。

#### 问：我可以修改代码来提取额外的图像相关属性吗？

答：是的，您可以自定义代码来提取图像的其他属性，例如颜色空间、像素深度或图像类型。

#### 问：图像信息提取的过程是否耗费大量资源或时间？

答：图像信息提取过程高效且针对性能进行了优化，确保对资源使用和处理时间的影响最小。

#### 问：识别和提取 PDF 文档中的图像信息对开发人员有什么好处？

答：开发人员可以深入了解 PDF 文档中图像的特点，从而让他们能够就图像处理、处理和优化做出明智的决策。

#### 问：此方法可以用于批量处理包含图像的PDF文档吗？

答：是的，该方法可以扩展用于批处理，通过遍历多个页面或文档，提取图像信息并执行与图像相关的任务。