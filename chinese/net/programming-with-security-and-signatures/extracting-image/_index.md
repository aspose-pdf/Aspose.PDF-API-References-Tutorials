---
title: 提取图像
linktitle: 提取图像
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地从 PDF 文档中提取图像。
type: docs
weight: 70
url: /zh/net/programming-with-security-and-signatures/extracting-image/
---

在许多情况下，从 PDF 文档中提取图像很有用。使用 Aspose.PDF for .NET，您可以使用以下源代码轻松提取图像：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。以下是必要的导入指令：

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要从中提取图像的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENTS DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## 第 3 步：从 PDF 文档中提取图像

现在我们将使用以下代码从 PDF 文档中提取图像：

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

在本例中，我们循环遍历 PDF 文档中表单的每个字段。如果找到签名字段，我们将提取相关图像并将其保存为 JPEG 文件。

### 使用 Aspose.PDF for .NET 提取图像的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## 结论

恭喜！现在您有了使用 Aspose.PDF for .NET 从 PDF 文档中提取图像的分步指南。您可以将此代码集成到您自己的项目中以提取图像并根据需要使用它们。

请务必查看官方 Aspose.PDF 文档以获取有关高级图像提取和 PDF 文档操作功能的更多信息。