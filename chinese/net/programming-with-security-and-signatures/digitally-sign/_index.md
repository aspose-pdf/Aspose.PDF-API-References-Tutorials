---
title: 数字签名
linktitle: 数字签名
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 对 PDF 文件进行数字签名。
type: docs
weight: 40
url: /zh/net/programming-with-security-and-signatures/digitally-sign/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 对 PDF 文件进行数字签名的过程。数字签名通过添加唯一的电子指纹来保证文档的真实性和完整性。

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
using System.Collections.Generic;
```

## 第三步：数字签名

第一步是对 PDF 文件进行数字签名。所提供的代码展示了如何使用 Aspose.PDF for .NET 进行数字签名。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

此代码加载 PDF 文件，创建具有指定外观的数字签名，然后使用添加的签名保存 PDF 文件。

## 第 4 步：签名验证

添加数字签名后，您可以检查 PDF 文件是否包含有效签名。

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         //做一点事
                     }
                 }
             }
         }
     }
}
```

此代码验证 PDF 文件的第一个签名，并在签名经过认证并具有特定权限时执行其他操作。

### 使用 Aspose.PDF for .NET 进行数字签名的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); //使用 PKCS7/PKCS7Detached 对象
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			//设置签名外观
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			//创建三种签名类型中的任何一种
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			//保存输出 PDF 文件
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) //有签名吗？
			{
				if (signature.VerifySigned(sigNames[0] as string)) //验证第一个
				{
					if (signature.IsCertified) //认证？
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) //获取访问权限
						{
							//做一点事
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

恭喜！您已经成功地使用 Aspose.PDF for .NET 对 PDF 文件执行了数字签名。本教程涵盖了从添加数字签名到验证其有效性的分步过程。您现在可以使用此功能通过数字签名保护您的 PDF 文件。