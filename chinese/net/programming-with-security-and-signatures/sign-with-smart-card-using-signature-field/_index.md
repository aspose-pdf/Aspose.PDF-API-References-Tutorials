---
title: 使用签名字段使用智能卡签名
linktitle: 使用签名字段使用智能卡签名
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 使用智能卡安全地签署您的 PDF 文件。
type: docs
weight: 120
url: /zh/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---

使用智能卡进行数字签名是一种对 PDF 文件进行签名的安全方式。使用 Aspose.PDF for .NET，您可以按照以下源代码使用签名字段和智能卡轻松地对 PDF 文件进行签名：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。以下是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要签名的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENTS DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第三步：复制并打开PDF文档

现在我们将使用以下代码复制并打开要签名的 PDF 文档：

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         //创建签名域
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         //在商店中选择证书
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         //使用必要的信息创建外部签名
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

## 第 4 步：验证签名

最后，我们使用`PdfFileSignature`班级。我们获取签名名称并一一检查。如果签名验证失败，则抛出异常。下面是相应的代码：

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

### 使用 Aspose.PDF for .NET 使用签名字段使用智能卡签名的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		//使用 Windows 证书存储中的证书选择进行签名
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

恭喜！现在，您有了一个分步指南，可以使用 Aspose.PDF for .NET 使用签名字段使用智能卡对 PDF 文件进行签名。您可以使用此代码将安全数字签名添加到您的 PDF 文档。

请务必查看官方 Aspose.PDF 文档，了解有关高级数字签名和证书管理功能的更多信息。