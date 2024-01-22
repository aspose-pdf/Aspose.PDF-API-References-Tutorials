---
title: 在 PDF 檔案中使用時間戳進行數位簽名
linktitle: 在 PDF 檔案中使用時間戳進行數位簽名
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中執行帶有時間戳記的數位簽章。
type: docs
weight: 50
url: /zh-hant/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 對帶有時間戳記的 PDF 檔案進行數位簽章的過程。帶有時間戳記的數位簽章透過添加帶有時間戳記的電子指紋來確保文件的真實性和完整性。

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
```

## 步驟3：帶有時間戳記的數位簽名

第一步是對 PDF 檔案執行帶有時間戳記的數位簽章。提供的程式碼顯示如何使用 Aspose.PDF for .NET 實作此簽章。

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

此程式碼載入 PDF 文件，使用 PFX 文件（私鑰）和指定的時間戳記參數建立帶有時間戳記的數位簽章。然後將簽名添加到 PDF 文件中並以後綴“”保存_出去」。

### 使用 Aspose.PDF for .NET 進行數位簽章的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); //使用者/密碼可以省略
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//建立三種簽名類型中的任一種
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		//儲存輸出 PDF 文件
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## 結論

恭喜！您已使用 Aspose.PDF for .NET 對 PDF 檔案成功執行了帶有時間戳記的數位簽章。本教學介紹了從建立簽名到保存更新的 PDF 檔案的逐步過程。現在您可以使用此功能為 PDF 文件添加帶有時間戳記的數位簽章。

### 在 PDF 檔案中使用時間戳進行數位簽章的常見問題解答

#### Q：使用時間戳進行數位簽章的目的是什麼？

答：時間戳數位簽章是在 PDF 檔案中加入帶有時間戳記的電子指紋，確保文件在特定時間點的真實性和完整性。

#### Q：開始本教學需要什麼先決條件？

答：在開始之前，請確保您對 C# 程式語言有基本的了解，並已安裝 Visual Studio，並安裝了適用於 .NET 的 Aspose.PDF 程式庫。

#### Q：如何設定我的開發環境？

答：請按照提供的步驟設定您的開發環境，包括在 Visual Studio 中建立新的 C# 專案並匯入必要的命名空間。

#### Q：如何在 PDF 中添加帶有時間戳記的數位簽章？

答：提供的範例程式碼示範如何載入 PDF 檔案、使用 PFX 檔案（私密金鑰）和指定的時間戳記設定來建立帶有時間戳記的數位簽章、將簽章新增至 PDF 檔案並儲存更新的檔案。

#### Q：什麼是 PFX 文件，為什麼在範例中使用它？

答：PFX（個人交換格式）檔案包含私鑰和憑證。它在這裡用於為數位簽名提供加密功能。確保將佔位符替換為您的 PFX 檔案和密碼。

#### Q：什麼是時間戳設定？

答：TimestampSettings 定義用於將電子時間戳記新增至簽署的時間戳伺服器的設定。它包括時間戳伺服器 URL 和可選的使用者憑證。

#### Q：除了範例中的伺服器之外，我還可以使用其他時間戳伺服器嗎？
答：是的，您可以使用任何相容的時間戳伺服器。替換 URL，並根據需要在中提供適當的使用者憑證`TimestampSettings`目的。

#### Q：指定簽名矩形的目的是什麼？

答：簽章矩形定義了 PDF 頁面上數位簽章外觀的位置和尺寸。調整這些值以根據需要放置簽名。

#### Q：如果簽章期間時間戳伺服器不可用怎麼辦？

答：如果簽署過程中時間戳伺服器不可用，則該過程可能會失敗或需要更長的時間。確保您的時間戳伺服器可靠且可存取。

#### Q：如何驗證簽名 PDF 中是否存在時間戳記？

答：您可以使用提供的範例程式碼檢查簽名的 PDF。這`TimestampSettings`您在簽名期間使用的內容應該可以在簽名詳細資訊中找到。

#### Q：帶有時間戳記的數位簽章具有法律約束力嗎？

答：帶有時間戳記的數位簽名在許多司法管轄區都具有法律價值，並且通常被認為比簡單的數位簽名更可靠。請諮詢您所在司法管轄區的法律專家以了解具體規定。

#### Q：我可以在 PDF 中新增多個帶有時間戳記的數位簽章嗎？

答：是的，您可以透過多次呼叫簽名建立過程，在 PDF 檔案中新增多個帶有時間戳記的數位簽章。每個簽名都有自己的時間戳記。