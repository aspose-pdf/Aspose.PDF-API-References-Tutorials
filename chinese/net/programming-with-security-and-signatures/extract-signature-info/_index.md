---
title: 提取签名信息
linktitle: 提取签名信息
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 提取签名信息。
type: docs
weight: 80
url: /zh/net/programming-with-security-and-signatures/extract-signature-info/
---

从 PDF 文档中提取签名信息的过程在各种情况下都非常有用。无论您需要验证签名文档的真实性还是分析用于签名的证书，Aspose.PDF for .NET 库都提供了一个方便的解决方案。在本教程中，我们将引导您使用提供的 C# 源代码逐步完成提取签名信息的过程。

## 要求

在我们开始之前，请确保您具备以下先决条件：

1. C# 编程语言的基础知识。
2. Aspose.PDF for .NET 库安装在您的系统上。
3. 具有一个或多个签名字段的有效 PDF 文档。

现在，让我们深入了解实施细节。

## 第 1 步：导入所需的库

首先，您需要将必要的库导入到您的 C# 项目中。在这种情况下，我们需要导入`Aspose.Pdf`和`System.IO`名称空间。这可以通过在 C# 文件的开头添加以下代码来完成：

```csharp
using Aspose.Pdf;
using System.IO;
```

## 第二步：设置文档路径

接下来，您需要设置要从中提取签名信息的 PDF 文档的路径。代替`"YOUR DOCUMENTS DIRECTORY"`在以下代码片段中包含文档的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## 第三步：提取签名信息

现在，让我们继续代码的主要部分，我们从 PDF 文档中提取签名信息。我们遍历文档表单中的每个字段并检查它是否是签名字段。如果找到签名字段，我们将继续提取证书。添加以下代码片段：

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             //提取证书
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## 第 4 步：提取证书

在这一步中，我们从签名字段中提取证书并将其保存为文件。提取的证书可以进一步分析或用于验证目的。下面的代码片段演示了提取和保存过程：

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## 步骤 5

: 保存证书

最后，我们将提取的证书保存为文件。在此示例中，证书以名称“input.cer”保存在指定目录中。您可以修改代码以满足您的要求。这是保存证书的代码片段：

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

就是这样！您已成功使用 Aspose.PDF for .NET 提取签名信息。随意将此代码集成到您自己的应用程序中或根据您的需要对其进行修改。

### 使用 Aspose.PDF for .NET 提取签名信息的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们分步介绍了如何使用 Aspose.PDF for .NET 库从 PDF 文档中提取签名信息。我们介绍了导入所需库、设置文档路径、提取签名信息、提取证书并将其保存到文件的过程。通过执行这些步骤，您可以轻松检索签名详细信息并根据需要使用它们。