---
title: 使用签名字段通过智能卡签名
linktitle: 使用签名字段通过智能卡签名
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 通过智能卡安全地签署您的 PDF 文件。
type: docs
weight: 120
url: /zh/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
使用智能卡进行数字签名是签署 PDF 文件的安全方式。使用 Aspose.PDF for .NET，您可以按照以下源代码使用签名字段和智能卡轻松签署 PDF 文件：

## 步骤 1：导入所需的库

开始之前，您需要导入 C# 项目所需的库。以下是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要签名的 PDF 文件的文件夹的路径。替换`"YOUR DOCUMENTS DIRECTORY"`在下面的代码中使用您的文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤3：复制并打开PDF文档

现在我们将复制并打开要签名的PDF文档，使用以下代码：

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         //创建签名字段
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         //在商店中选择证书
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         //使用必要信息创建外部签名
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## 步骤 4：验证签名

最后，我们使用`PdfFileSignature`类，我们获取签名名称，然后逐个进行校验，如果签名校验不通过，则会抛出异常，下面是对应的代码：

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### 使用 Aspose.PDF for .NET 使用签名字段通过智能卡签名的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		//使用 Windows 证书存储区中的证书选择进行签名
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		//在商店中手动选择证书
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## 结论

恭喜！现在，您已经获得了使用 Aspose.PDF for .NET 的签名字段通过智能卡对 PDF 文件进行签名的分步指南。您可以使用此代码将安全数字签名添加到您的 PDF 文档中。

请务必查看官方 Aspose.PDF 文档，以获取有关高级数字签名和证书管理功能的更多信息。

### 常见问题解答

#### 问：使用签名栏进行智能卡数字签名有什么好处？

答：使用智能卡进行数字签名的签名字段会在 PDF 中指定一个区域用于签名。这可以提高文档清晰度并确保签名的真实性。

#### 问：Aspose.PDF for .NET 库如何实现带有签名字段的基于智能卡的数字签名？

答：Aspose.PDF for .NET 简化了创建签名字段、选择智能卡证书以及将数字签名应用于 PDF 文档内特定区域的过程。

#### 问：为什么选择特定的证书对于基于智能卡的签名很重要？

答：选择特定证书可让您唯一地识别签名者并确保签名的完整性。这有助于建立信任并遵守数字签名标准。

#### 问：提供的源代码如何处理基于智能卡的带有签名字段的签名过程？

答：源代码演示了如何创建签名字段、选择智能卡证书以及如何应用具有特定签名信息的数字签名。它还演示了如何验证签名的有效性。

#### 问：我可以自定义签名栏的外观吗？

答：是的，您可以自定义签名域的外观，例如其大小、位置和视觉呈现，以与您的文档的布局保持一致。

#### 问：如果在验证步骤中签名验证失败会发生什么？

答：如果签名验证失败，则会抛出异常，表明该签名无效。这确保只接受有效且受信任的签名。

#### 问：我可以将多个签名字段和基于智能卡的签名应用于单个 PDF 文档吗？

答：当然，您可以将多个签名字段和基于智能卡的签名应用于同一 PDF 文档的不同区域，从而提供多层安全性。

#### 问：使用签名栏如何增强整体文档签名流程？

答：使用签名栏可以简化文档签名流程，因为它可以引导签名者将其签名放在指定区域，从而使签名流程更加有序、更加用户友好。

#### 问：使用基于智能卡的签名的签名字段有什么限制吗？

答：使用基于智能卡的签名字段没有固有限制。但是，重要的是确保所选的签名字段位置不会遮挡重要的文档内容。

#### 问：在哪里可以找到有关使用签名栏实现基于智能卡签名的进一步帮助或支持？

答：如需更多指导和支持，您可以参考 Aspose.PDF 官方文档和社区论坛，它们为实施安全数字签名提供了宝贵的见解和解决方案。