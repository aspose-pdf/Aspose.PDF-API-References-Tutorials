---
title: PDF文件中的突出显示字符
linktitle: PDF文件中的突出显示字符
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 突出显示 PDF 文件中的字符。
type: docs
weight: 240
url: /zh/net/programming-with-text/highlight-character-in-pdf/
---
在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库突出显示 PDF 文件中的字符。我们将使用提供的 C# 源代码逐步介绍突出显示 PDF 中的字符的过程。

## 要求

开始之前，请确保您已准备好以下物品：

- 已安装 Aspose.PDF for .NET 库。
- 对 C# 编程有基本的了解。

## 步骤 1：设置文档目录

首先，您需要设置输入 PDF 文件所在目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`在`dataDir`变量，其中包含您的 PDF 文件的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载 PDF 文档

接下来，我们使用`Aspose.Pdf.Document`班级。

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## 步骤 3：将 PDF 转换为图像

为了突出显示字符，我们使用`PdfConverter`类。我们设置转换的分辨率，并将图像检索为`Bitmap`目的。

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## 第四步：突出人物

我们循环遍历 PDF 文档的每一页，并使用`TextFragmentAbsorber`对象来查找页面中的所有单词。然后，我们遍历文本片段、段和字符，并使用矩形突出显示它们。

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //设置比例和变换
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     //循环浏览页面
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //查找页面中的所有单词
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         //循环遍历文本片段
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 //突出显示字符
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 //循环遍历片段
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     //亮点部分
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     //循环遍历字符
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         //突出人物
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## 步骤 5：保存输出图像

最后，我们将修改后带有突出显示字符的图像保存到指定的输出文件中。

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### 使用 Aspose.PDF for .NET 在 PDF 中突出显示字符的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				//创建 TextAbsorber 对象来查找所有单词
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				//获取提取的文本片段
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				//循环遍历片段
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库突出显示 PDF 文档中的字符。通过遵循分步指南并执行提供的 C# 代码，您可以突出显示 PDF 中的字符并将输出保存为图像。

### 常见问题解答

#### 问： “在 PDF 文件中突出显示字符”教程的目的是什么？

答：“突出显示 PDF 文件中的字符”教程解释了如何使用 .NET 的 Aspose.PDF 库突出显示 PDF 文档中的字符。该教程提供了分步指南和 C# 源代码来实现此目的。

#### 问：为什么我要突出显示 PDF 文档中的字符？

答：突出显示 PDF 文档中的字符可用于多种目的，例如强调特定内容或使某些文本更清晰、更易区分。

#### 问：如何设置文档目录？

A：设置文档目录：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`变量为输入 PDF 文件所在目录的路径。

#### 问：如何加载 PDF 文档并将其转换为图像？

答：在教程中，`Aspose.Pdf.Document`类用于加载输入 PDF 文档。然后，`PdfConverter`类用于将 PDF 文档转换为图像。设置图像的分辨率，并将图像作为`Bitmap`目的。

#### 问：如何突出显示 PDF 文档图像中的字符？

答：本教程将指导您循环遍历 PDF 文档的每一页，使用`TextFragmentAbsorber`，并遍历文本片段、段和字符，使用矩形突出显示它们。

#### 问：我可以自定义突出显示的字符和片段的外观吗？

答：是的，您可以通过修改绘图操作中使用的颜色和样式来自定义突出显示的字符和段的外观。

#### 问：如何保存修改后的带有突出显示字符的图像？

答：本教程演示如何使用`Save`方法`Bitmap`班级。

#### 问：本教程是否需要有效的 Aspose 许可证？

答：是的，本教程需要有效的 Aspose 许可证才能正常运行。您可以从 Aspose 网站购买完整许可证或获取 30 天的临时许可证。