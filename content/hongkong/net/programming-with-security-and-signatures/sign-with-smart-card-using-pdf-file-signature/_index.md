---
title: 使用 PDF 檔案簽名透過智慧卡進行簽名
linktitle: 使用 PDF 檔案簽名透過智慧卡進行簽名
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 透過智慧卡安全地簽署您的 PDF 檔案。
type: docs
weight: 110
url: /zh-hant/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
使用智慧卡進行數位簽章是簽署 PDF 檔案的安全方式。使用 Aspose.PDF for .NET，您可以按照以下原始程式碼輕鬆使用智慧卡對 PDF 檔案進行簽署：

## 步驟1：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。以下是必要的導入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定包含要簽署的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENTS DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 3 步：載入 PDF 文檔

現在我們將使用以下程式碼載入要簽署的 PDF 文件：

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## 步驟4：使用智慧卡進行簽名

在此步驟中，我們將使用智慧卡執行簽名`PdfFileSignature`類別來自`Facades`圖書館.我們從 Windows 憑證儲存中選擇智慧卡憑證並指定必要的簽章資訊。這是對應的程式碼：

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     //選擇商店中的證書
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## 第 5 步：驗證簽名

最後，我們使用以下命令驗證已簽署 PDF 檔案的簽名：`PdfFileSignature`班級。我們拿到簽名名字，一一核對。如果簽名驗證失敗，則會拋出例外狀況。這是對應的程式碼：

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

### 使用 Aspose.PDF for .NET 使用 Pdf 檔案簽章透過智慧卡進行簽署的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	//使用 Windows 憑證儲存空間中的憑證選擇進行簽名
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	//手動選擇商店中的證書
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

## 結論

恭喜！現在，您已獲得使用 Aspose.PDF for .NET 透過智慧卡對 PDF 檔案進行簽署的逐步指南。您可以使用此程式碼為 PDF 文件新增安全數位簽章。

請務必查看官方 Aspose.PDF 文檔，以取得更多有關高級數位簽章和憑證管理功能的資訊。

### 常見問題解答

#### Q：為什麼我應該考慮使用智能卡簽署 PDF 文件？

答：使用智慧卡簽署 PDF 檔案可以確保文件的真實性和完整性，從而增強安全性。基於智慧卡的簽章提供了更高層次的信任和合規性。

#### Q：基於智慧卡的數位簽章如何運作？

答：基於智慧卡的數位簽章涉及使用儲存在智慧卡上的加密金鑰來建立唯一的數位簽章。此簽章附加到 PDF 文件中，允許收件者驗證文件的來源和完整性。

#### Q：Aspose.PDF for .NET 在基於智慧卡的簽章中的作用是什麼？

答：Aspose.PDF for .NET 提供了一套全面的工具和函式庫，以促進 PDF 檔案基於智慧卡的數位簽章。它簡化了流程並確保安全的文件簽名。

#### Q：我可以選擇特定的智慧卡憑證進行簽名嗎？

答：是的，您可以從 Windows 憑證儲存區中選擇特定的智慧卡憑證進行簽署。 Aspose.PDF for .NET 可讓您將憑證選擇無縫整合到您的應用程式中。

#### Q：所提供的原始程式碼如何處理基於智慧卡的簽章？

答：原始程式碼示範如何綁定PDF文件、選擇智慧卡憑證、指定簽名資訊以及建立數位簽章。它也展示瞭如何驗證簽名的有效性。

#### Q：我可以使用智慧卡在單一 PDF 檔案中套用多個簽章嗎？

答：當然，您可以將多個基於智慧卡的簽章套用至單一 PDF 檔案。每個簽名都是唯一的，有助於提高文件的整體安全性。

#### Q：如果簽名在驗證過程中驗證失敗怎麼辦？

答：如果簽名驗證失敗，會拋出異常，表示簽名無效。這確保了僅接受有效且可信的簽名。

#### Q：基於智慧卡的簽章是否與所有類型的 PDF 文件相容？

答：是的，基於智慧卡的簽章與所有類型的 PDF 文件相容。您可以將數位簽章套用至各種類型的 PDF 文件，包括表單、報告等。

#### Q：如何了解更多有關高級數位簽章和憑證管理的資訊？

答：瀏覽 Aspose.PDF 官方文檔，以詳細了解高級數位簽章功能、憑證管理和確保文件安全的最佳實務。

#### Q：在哪裡可以找到實施基於智慧卡的簽名的進一步幫助或支援？

答：如需更多指導和支持，請造訪 Aspose.PDF 社群論壇或參閱文件以取得有關基於智慧卡的簽名的全面資訊。