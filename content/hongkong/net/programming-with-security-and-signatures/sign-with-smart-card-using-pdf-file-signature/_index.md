---
title: 使用 PDF 檔案簽名透過智慧卡進行簽名
linktitle: 使用 PDF 檔案簽名透過智慧卡進行簽名
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用智慧卡和 Aspose.PDF for .NET 對 PDF 檔案進行簽署。請遵循此安全數位簽章逐步指南。
type: docs
weight: 110
url: /zh-hant/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## 介紹

在數位時代，保護文件比以往任何時候都更加重要。無論是合約、協議或任何敏感資訊，確保文件真實且未被篡改至關重要。輸入數位簽章！今天，我們將深入研究如何使用智慧卡和 Aspose.PDF for .NET 對 PDF 檔案進行簽署。這個強大的程式庫允許開發人員有效地操作和建立 PDF 文檔，包括添加安全的數位簽章。那麼，拿起您的智慧卡，讓我們開始吧！

## 先決條件

在我們深入了解簽署 PDF 文件的細節之前，讓我們先確保您擁有所需的一切。以下是幫助您做好準備的清單：

1.  Aspose.PDF for .NET：請確定您已安裝 Aspose.PDF 庫。您可以從[地點](https://releases.aspose.com/pdf/net/).
2. Visual Studio：您可以在其中編寫和執行 .NET 程式碼的開發環境。
3. 智慧卡：您需要一張安裝了有效數位憑證的智慧卡。
4. 對 C# 的基本了解：熟悉 C# 程式設計將很有幫助，因為我們將用這種語言編寫程式碼片段。
5. PDF 文件：範例 PDF 文件（例如`blank.pdf`）來測試我們的簽名流程。

滿足這些先決條件後，您就可以開始研究程式碼了！

## 導入包

首先，讓我們導入必要的套件。您需要在專案中新增對 Aspose.PDF 庫的引用。您可以這樣做：

1. 打開視覺工作室。
2. 建立一個新項目或開啟一個現有項目。
3. 在解決方案資源管理器中右鍵單擊您的專案並選擇`Manage NuGet Packages`.
4. 搜尋`Aspose.PDF`並安裝最新版本。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

現在我們已經導入了必要的套件，讓我們逐步分解程式碼。

## 第 1 步：設定您的文檔

我們流程的第一步是設定我們想要簽署的 PDF 文件。您可以按照以下方法執行此操作：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
在此程式碼片段中，我們定義文檔目錄的路徑並建立一個實例`Document`類別使用名為的範例 PDF 文件`blank.pdf`。確保更換`"YOUR DOCUMENTS DIRECTORY"`與 PDF 所在的實際路徑。

## 步驟2：初始化PdfFileSignature

接下來，我們將初始化`PdfFileSignature`類，負責處理簽名過程。

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
在這裡，我們建立一個實例`PdfFileSignature`並將其綁定到我們的 PDF 文件。這將為簽署文件做好準備。

## 第 3 步：存取智慧卡證書

現在到了關鍵部分——存取儲存在智慧卡上的數位憑證。我們可以這樣做：

### 開啟證書存儲

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
我們開啟位於目前使用者設定檔中的憑證儲存。這使我們能夠存取您電腦上安裝的證書，包括您智慧卡上的證書。

### 選擇證書

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
此程式碼提示使用者從集合中選擇一個憑證。使用者介面將顯示所有可用的證書，允許您選擇與您的智慧卡關聯的證書。

## 第 4 步：建立外部簽名

選擇憑證後，下一步是使用所選憑證建立外部簽章。

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
在這裡，我們建立一個實例`ExternalSignature`使用選定的證書。該物件將用於簽署 PDF 文件。

## 第5步：設定簽名外觀

現在，讓我們來設定簽名的外觀。您可以在此處自訂簽名在文件上的外觀。

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
在此程式碼片段中，我們透過提供圖像檔案（如徽標或簽名圖形）的路徑來指定簽名的外觀。確保更換`"demo.png"`與您要使用的實際影像。

## 第 6 步：簽署 PDF

一切設定完畢後，就可以簽署 PDF 文件了！

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
在這一步中，我們稱`Sign`我們的方法`pdfSign`目的。每個參數的意義如下：
- `1`：簽名將出現的頁碼。
- `"Reason"`：簽署文件的原因。
- `"Contact"`：簽名者的聯絡資訊。
- `"Location"`：簽名者的位置。
- `true`：是否建立可見簽名。
- `new System.Drawing.Rectangle(100, 100, 200, 200)`：PDF 上簽名的位置和大小。
- `externalSignature`：我們之前建立的簽名對象。

最後，我們將簽名後的文檔儲存為`externalSignature2.pdf`.

## 步驟7：驗證簽名

簽署文件後，必須驗證簽名是否有效。具體做法如下：

### 初始化驗證過程

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
我們建立一個新實例`PdfFileSignature`對於已簽署的文件。然後，我們檢索文件中存在的所有簽名的名稱。

### 檢查簽名有效性

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
我們循環遍歷每個簽名名稱並驗證其有效性。如果簽章驗證失敗，則會拋出異常，表示簽章無效。

## 結論

現在你就擁有了！您已透過 Aspose.PDF for .NET 使用智慧卡成功簽署了 PDF 文件。此過程不僅可以保護您的文檔，還可以增加一層在當今數位世界中至關重要的真實性。無論您是在處理合約、法律文件還是任何敏感訊息，了解如何實施數位簽名都是一項寶貴的技能。 

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在.NET 應用程式中建立、操作和轉換 PDF 文件。

### 我需要智慧卡來簽署 PDF 嗎？
雖然智慧卡不是強制性的，但強烈建議使用它來實現安全數位簽名，因為它提供了額外的安全層。

### 我可以使用任何 PDF 檔案進行簽名嗎？
是的，您可以使用任何 PDF 文件，但請確保它不受密碼保護。如果是，您需要先解鎖。

### 如果我沒有數位憑證怎麼辦？
您可以從受信任的憑證授權單位 (CA) 取得數位憑證或使用自簽名憑證進行測試。

### 是否有 Aspose.PDF 的試用版？
是的，您可以從以下位置下載免費試用版[阿斯普斯網站](https://releases.aspose.com/).