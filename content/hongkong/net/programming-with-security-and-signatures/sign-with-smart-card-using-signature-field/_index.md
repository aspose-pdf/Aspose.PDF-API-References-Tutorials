---
title: 使用簽名字段透過智慧卡進行簽名
linktitle: 使用簽名字段透過智慧卡進行簽名
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 透過智慧卡安全地簽署您的 PDF 檔案。
type: docs
weight: 120
url: /zh-hant/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
使用智慧卡進行數位簽章是簽署 PDF 檔案的安全方式。使用 Aspose.PDF for .NET，您可以按照以下原始程式碼使用簽名欄位和智慧卡輕鬆簽署 PDF 檔案：

## 步驟1：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。以下是必要的導入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定包含要簽署的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENTS DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 3：複製並開啟 PDF 文檔

現在我們將使用以下程式碼複製並開啟要簽署的PDF文件：

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         //建立簽名字段
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         //選擇商店中的證書
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         //使用必要的資訊建立外部簽名
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

## 第 4 步：驗證簽名

最後，我們使用以下命令驗證已簽署 PDF 檔案的簽名：`PdfFileSignature`班級。我們拿到簽名名字，一一核對。如果簽名驗證失敗，則會拋出例外狀況。這是對應的程式碼：

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

### 使用 Aspose.PDF for .NET 使用簽章欄位透過智慧卡進行簽署的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		//使用 Windows 憑證儲存空間中的憑證選擇進行簽名
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		//手動選擇商店中的證書
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

## 結論

恭喜！現在，您已獲得使用 Aspose.PDF for .NET 的簽名字段，透過智慧卡對 PDF 文件進行簽署的逐步指南。您可以使用此程式碼為 PDF 文件新增安全數位簽章。

請務必查看官方 Aspose.PDF 文檔，以取得更多有關高級數位簽章和憑證管理功能的資訊。

### 常見問題解答

#### Q：使用簽章欄位透過智慧卡進行數位簽章有什麼好處？

答：使用智慧卡的簽章欄位進行數位簽章可在 PDF 中提供套用簽章的指定區域。這增強了文件的清晰度並確保簽名的真實性。

#### Q：Aspose.PDF for .NET 函式庫如何透過簽章欄位促進基於智慧卡的數位簽章？

答：Aspose.PDF for .NET 簡化了建立簽章欄位、選擇智慧卡憑證以及將數位簽章套用至 PDF 文件中特定區域的過程。

#### Q：為什麼選擇特定憑證對於基於智慧卡的簽章很重要？

答：選擇特定的憑證可以唯一標識簽署者並保證簽名的完整性。這有助於建立信任並遵守數位簽章標準。

#### Q：所提供的原始程式碼如何使用簽章欄位處理基於智慧卡的簽名過程？

答：原始程式碼示範如何建立簽章欄位、選擇智慧卡憑證以及套用具有特定簽章資訊的數位簽章。它也展示瞭如何驗證簽名的有效性。

#### Q：我可以自訂簽名欄位的外觀嗎？

答：是的，您可以自訂簽名欄位的外觀，例如其大小、位置和視覺表示，以與文件的佈局保持一致。

#### Q：如果簽名在驗證步驟中驗證失敗怎麼辦？

答：如果簽名驗證失敗，會拋出異常，表示簽名無效。這確保了僅接受有效且可信的簽名。

#### Q：我可以將多個簽章欄位和基於智慧卡的簽章套用至單一 PDF 文件嗎？

答：當然，您可以將多個簽章欄位和基於智慧卡的簽章套用至相同 PDF 文件的不同區域，從而提供多層安全性。

#### Q：使用簽章欄位如何增強整個文件簽章流程？

答：使用簽章欄位可以簡化文件簽章過程，因為它可以引導簽章者將簽章放在指定區域，使簽章過程更有條理、更人性化。

#### Q：在基於智慧卡的簽章中使用簽章欄位是否有任何限制？

答：使用基於智慧卡的簽章的簽章欄位沒有固有的限制。但是，重要的是要確保所選的簽章欄位位置不會掩蓋重要的文件內容。

#### Q：在哪裡可以找到有關使用簽名字段實施基於智慧卡的簽名的進一步幫助或支援？

答：如需更多指導和支持，您可以參考 Aspose.PDF 官方文件和社群論壇，它們為實現安全數位簽章提供了寶貴的見解和解決方案。