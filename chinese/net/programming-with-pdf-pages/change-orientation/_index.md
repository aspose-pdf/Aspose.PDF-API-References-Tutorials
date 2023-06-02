---
title: 改变方向
linktitle: 改变方向
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 更改 PDF 页面方向的分步指南。易于在您的项目中遵循和实施。
type: docs
weight: 10
url: /zh/net/programming-with-pdf-pages/change-orientation/
---
在本教程中，我们将逐步引导您使用 Aspose.PDF for .NET 更改 PDF 文档的页面方向。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 更改 PDF 文档的页面方向。

## 先决条件
在开始之前，请确保您具备以下条件：

- C#编程语言的基本知识
- 安装在您的开发环境中的 Aspose.PDF for .NET

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是您的输入 PDF 文件所在的位置，也是您要保存修改后的输出 PDF 文件的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载 PDF 文档
然后您可以使用从输入文件加载 PDF 文档`Document`Aspose.PDF 类。请务必指定 PDF 文件的正确路径。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第 3 步：更改页面方向
现在我们将浏览文档的每一页并更改其方向。对于每个页面，我们修改媒体框的尺寸（`MediaBox`) 通过交换宽度和高度，然后我们调整媒体框的坐标以保持页面的位置。最后，我们将页面旋转设置为 90 度。

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## 第 4 步：保存修改后的 PDF 文档
最后，您可以使用以下命令将修改后的 PDF 文档保存到输出文件`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的 Change Orientation 示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	//我们必须向上移动页面以补偿不断变化的页面大小
	//（页面的下边缘是 0,0，信息通常从
	//页面顶部。这就是为什么我们将 lover edge 上移到两者之间的差异
	//新旧高度。
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//有时我们还需要设置 CropBox（如果它在原始文件中设置）
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//设置页面旋转角度
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
//保存输出文件
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 更改 PDF 文档的页面方向。按照上述步骤，您可以轻松地在自己的项目中实现此功能。随意进一步探索 Aspose.PDF 文档以发现处理 PDF 文件的其他有用功能。