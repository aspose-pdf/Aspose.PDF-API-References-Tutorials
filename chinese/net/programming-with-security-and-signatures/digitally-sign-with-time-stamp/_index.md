---
title: 使用时间戳进行数字签名
linktitle: 使用时间戳进行数字签名
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件上执行带有时间戳的数字签名。
type: docs
weight: 50
url: /zh/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 对带有时间戳的 PDF 文件进行数字签名的过程。带时间戳的数字签名通过添加带时间戳的电子指纹来保证文档的真实性和完整性。

## 第 1 步：先决条件

在开始之前，请确保您具备以下先决条件：

- C#编程语言的基础知识
- 在您的计算机上安装 Visual Studio
- 已安装用于 .NET 的 Aspose.PDF 库

## 第二步：环境搭建

首先，请按照以下步骤设置您的开发环境：

1. 打开 Visual Studio 并创建一个新的 C# 项目。
2. 将所需的命名空间导入您的代码文件：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## 第三步：带时间戳的数字签名

第一步是对 PDF 文件执行带有时间戳的数字签名。提供的代码显示了如何使用 Aspose.PDF for .NET 实现此签名。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

此代码加载 PDF 文件，使用 PFX 文件（私钥）和指定的时间戳参数创建带有时间戳的数字签名。然后将签名添加到 PDF 文件并使用后缀“保存”_出去”。

### 使用 Aspose.PDF for .NET 使用时间戳进行数字签名的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); //用户/密码可以省略
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//创建三种签名类型中的任何一种
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		//保存输出 PDF 文件
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## 结论

恭喜！您已经成功地使用 Aspose.PDF for .NET 在 PDF 文件上执行了带有时间戳的数字签名。本教程涵盖了从创建签名到保存更新的 PDF 文件的分步过程。您现在可以使用此功能为您的 PDF 文件添加带时间戳的数字签名。