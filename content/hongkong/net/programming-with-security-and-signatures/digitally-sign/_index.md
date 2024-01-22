---
title: 數位登入 PDF 文件
linktitle: 數位登入 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 對 PDF 檔案進行數位簽章。
type: docs
weight: 40
url: /zh-hant/net/programming-with-security-and-signatures/digitally-sign/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 對 PDF 檔案進行數位簽署的過程。數位簽章透過添加唯一的電子指紋來保證文件的真實性和完整性。

## 第 1 步：先決條件

在開始之前，請確保您具備以下先決條件：

- C# 程式語言的基礎知識
- 在您的電腦上安裝 Visual Studio
- 已安裝適用於 .NET 的 Aspose.PDF 庫

## 第2步：環境設定

首先，請按照以下步驟設定您的開發環境：

1. 開啟 Visual Studio 並建立一個新的 C# 專案。
2. 將所需的命名空間匯入到您的程式碼檔案中：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## 第三步：數位簽名

第一步是對 PDF 檔案進行數位簽章。提供的程式碼顯示如何使用 Aspose.PDF for .NET 進行數位簽章。

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

此程式碼會載入 PDF 文件，建立具有指定外觀的數位簽名，然後使用新增的簽名儲存 PDF 文件。

## 第四步：簽名驗證

新增數位簽名後，您可以檢查PDF檔案是否包含有效簽名。

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
                         //做一點事
                     }
                 }
             }
         }
     }
}
```

此程式碼驗證 PDF 檔案的第一個簽名，並在簽名經過認證且具有特定權限時執行其他操作。

### 使用 Aspose.PDF for .NET 進行數位簽章的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); //使用 PKCS7/PKCS7Detached 對象
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			//設定簽名外觀
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			//建立三種簽名類型中的任一種
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			//儲存輸出 PDF 文件
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) //有簽名嗎？
			{
				if (signature.VerifySigned(sigNames[0] as string)) //驗證第一個
				{
					if (signature.IsCertified) //已認證？
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) //取得存取權限
						{
							//做一點事
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

## 結論

恭喜！您已使用 Aspose.PDF for .NET 對 PDF 檔案成功執行了數位簽章。本教程介紹了從添加數位簽名到驗證其有效性的逐步過程。現在您可以使用此功能透過數位簽章來保護您的 PDF 檔案。

### 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學將引導您完成使用 Aspose.PDF for .NET 對 PDF 檔案進行數位簽章的過程。數位簽章添加電子指紋以確保文件的真實性和完整性。

#### Q：開始之前需要什麼先決條件？

答：在開始之前，請確保您對 C# 程式語言有基本的了解，並已安裝 Visual Studio，並安裝了適用於 .NET 的 Aspose.PDF 程式庫。

#### Q：如何建構開發環境？

答：請依照提供的步驟設定開發環境，包括在 Visual Studio 中建立新的 C# 項目，並匯入所需的命名空間。

#### Q：如何在 PDF 檔案中新增數位簽章？

答：提供的範例程式碼示範如何載入 PDF 檔案、建立數位簽章、指定外觀以及儲存簽署的 PDF 檔案。數位簽名是使用添加的`Certify`的方法`PdfFileSignature`目的。

#### Q：如何驗證數位簽章的有效性？

A：新增數位簽章後，您可以使用範例程式碼驗證簽章的有效性。它檢查簽名是否經過認證並具有特定的存取權限。

####  Q：什麼是`PKCS7` object represent?

答： 的`PKCS7`物件用於為數位簽章提供加密功能。它用於在提供的範例程式碼中建立數位簽名。

#### Q：我可以自訂數位簽章的外觀嗎？

答：是的，您可以透過在檔案中指定影像的路徑來自訂數位簽章的外觀。`SignatureAppearance`的財產`PdfFileSignature`目的。

#### Q：如果簽名無效怎麼辦？

A：如果簽章無效，則驗證程序將會失敗，驗證碼區塊內的對應操作將不會被執行。

#### Q：如何確保我的數位簽章的安全？

答：數位簽章在設計上是安全的，並使用加密技術來確保真實性和完整性。確保您的私鑰安全並遵循處理數位簽章的最佳實務。

#### Q：我可以在 PDF 中新增多個數位簽章嗎？

答：是的，您可以使用以下命令在 PDF 檔案中新增多個數位簽名`PdfFileSignature`對象的`Sign`或者`Certify`方法。每個簽名都有自己的外觀和配置。