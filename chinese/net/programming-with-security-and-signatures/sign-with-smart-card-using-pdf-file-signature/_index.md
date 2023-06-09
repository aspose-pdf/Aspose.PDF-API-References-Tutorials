---
title: 使用 Pdf 文件签名对智能卡进行签名
linktitle: 使用 Pdf 文件签名对智能卡进行签名
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 使用智能卡安全地签署您的 PDF 文件。
type: docs
weight: 110
url: /zh/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---

使用智能卡进行数字签名是一种对 PDF 文件进行签名的安全方式。使用 Aspose.PDF for .NET，您可以按照以下源代码使用智能卡轻松地签署 PDF 文件：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。以下是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要签名的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENTS DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 3 步：加载 PDF 文档

现在我们将使用以下代码加载要签名的 PDF 文档：

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## 第四步：使用智能卡进行签名

在此步骤中，我们将使用智能卡执行签名`PdfFileSignature`班级从`Facades`图书馆。我们从 Windows 证书存储中选择智能卡证书并指定必要的签名信息。下面是相应的代码：

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     //在商店中选择证书
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## 第 5 步：验证签名

最后，我们使用`PdfFileSignature`班级。我们获取签名名称并一一检查。如果签名验证失败，则抛出异常。下面是相应的代码：

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

### 使用 Aspose.PDF for .NET 使用 Pdf 文件签名使用智能卡签名的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	//使用 Windows 证书存储中的证书选择进行签名
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	//在商店中手动选择证书
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

恭喜！您现在有了使用 Aspose.PDF for .NET 使用智能卡签署 PDF 文件的分步指南。您可以使用此代码将安全数字签名添加到您的 PDF 文档。

请务必查看官方 Aspose.PDF 文档，了解有关高级数字签名和证书管理功能的更多信息。