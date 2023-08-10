---
title: 数字登录 PDF 文件
linktitle: 数字登录 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 对 PDF 文件进行数字签名。
type: docs
weight: 40
url: /zh/net/programming-with-security-and-signatures/digitally-sign/
---
在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 对 PDF 文件进行数字签名的过程。数字签名通过添加唯一的电子指纹来保证文档的真实性和完整性。

## 第 1 步：先决条件

在开始之前，请确保您具备以下先决条件：

- C# 编程语言的基础知识
- 在您的计算机上安装 Visual Studio
- 已安装适用于 .NET 的 Aspose.PDF 库

## 第2步：环境设置

首先，请按照以下步骤设置您的开发环境：

1. 打开 Visual Studio 并创建一个新的 C# 项目。
2. 将所需的命名空间导入到您的代码文件中：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## 第三步：数字签名

第一步是对 PDF 文件进行数字签名。提供的代码展示了如何使用 Aspose.PDF for .NET 进行数字签名。

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

## 第四步：签名验证

添加数字签名后，您可以检查PDF文件是否包含有效签名。

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

此代码验证 PDF 文件的第一个签名，并在签名经过认证且具有特定权限时执行其他操作。

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
			//创建三种签名类型中的任意一种
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
					if (signature.IsCertified) //已认证？
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

恭喜！您已使用 Aspose.PDF for .NET 对 PDF 文件成功执行了数字签名。本教程介绍了从添加数字签名到验证其有效性的分步过程。您现在可以使用此功能通过数字签名来保护您的 PDF 文件。

### 常见问题解答

#### 问：本教程的目的是什么？

答：本教程将指导您完成使用 Aspose.PDF for .NET 对 PDF 文件进行数字签名的过程。数字签名添加电子指纹以确保文档的真实性和完整性。

#### 问：开始之前需要什么先决条件？

答：开始之前，请确保您对 C# 编程语言有基本的了解，已安装 Visual Studio，并安装了适用于 .NET 的 Aspose.PDF 库。

#### 问：如何搭建开发环境？

答：按照提供的步骤设置开发环境，包括在 Visual Studio 中创建新的 C# 项目，并导入所需的命名空间。

#### 问：如何向 PDF 文件添加数字签名？

答：提供的示例代码演示了如何加载 PDF 文件、创建数字签名、指定外观以及保存签名的 PDF 文件。数字签名是使用添加的`Certify`的方法`PdfFileSignature`目的。

#### 问：如何验证数字签名的有效性？

A：添加数字签名后，您可以使用示例代码验证签名的有效性。它检查签名是否经过认证并具有特定的访问权限。

#### 问：什么是`PKCS7` object represent?

答： 的`PKCS7`对象用于为数字签名提供加密功能。它用于在提供的示例代码中创建数字签名。

#### 问：我可以自定义数字签名的外观吗？

答：是的，您可以通过在文件中指定图像的路径来自定义数字签名的外观。`SignatureAppearance`的财产`PdfFileSignature`目的。

#### 问：如果签名无效怎么办？

A：如果签名无效，则验证过程将失败，验证码块内的相应操作将不会被执行。

#### 问：如何确保我的数字签名的安全？

答：数字签名在设计上是安全的，并使用加密技术来确保真实性和完整性。确保您的私钥安全并遵循处理数字签名的最佳实践。

#### 问：我可以在 PDF 中添加多个数字签名吗？

答：是的，您可以使用以下命令向 PDF 文件添加多个数字签名`PdfFileSignature`对象的`Sign`或者`Certify`方法。每个签名都有自己的外观和配置。