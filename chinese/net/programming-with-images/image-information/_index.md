---
title: 图像信息
linktitle: 图像信息
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中提取图像信息。
type: docs
weight: 160
url: /zh/net/programming-with-images/image-information/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 从 PDF 文件中提取有关图像的信息。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

确保设置正确的文档目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源 PDF 文件

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 第 3 步：设置默认分辨率

在此步骤中，我们将为图像设置默认分辨率。在示例中，默认分辨率设置为 72。

```csharp
int defaultResolution = 72;
```

## 第 4 步：初始化对象和计数器

在此步骤中，我们将初始化检索图像信息所需的对象和计数器。

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## 第 5 步：循环浏览文档第一页上的运算符

在此步骤中，我们将遍历文档第一页上的运算符来识别与图像相关的操作。

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## 第六步：管理算子，提取图像信息

在此步骤中，我们将管理不同类型的运算符并提取有关图像的信息。

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//处理 GSave 和 GRestore 操作以进行转换
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
//处理图片的Do操作
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
//插入要堆叠的对象
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
//获取文档第一页上的所有运算符
foreach (Operator op in doc.Pages[1].Contents)
{
	//使用 GSave/GRestore 运算符将转换恢复为先前设置
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	//实例化 ConcatenateMatrix 对象，因为它定义了当前转换矩阵。
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	//创建从资源中提取对象的 Do 运算符。它绘制 Form 对象和 Image 对象
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//保存之前的状态并将当前状态压入栈顶
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		//丢弃当前状态并恢复以前的状态
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
		//如果这是一个图像绘制操作符
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			//创建 XImage 对象以保存第一个 pdf 页面的图像
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			//获取图像尺寸
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			//获取图片的高宽信息
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			//根据以上信息计算分辨率
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			//显示每个图像的尺寸和分辨率信息
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## 结论

恭喜！您现在已经了解了如何使用 Aspose.PDF for .NET 在 PDF 文件中提取图像信息。您可以将此信息用于应用程序中的各种图像处理任务。