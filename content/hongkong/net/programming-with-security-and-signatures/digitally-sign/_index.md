---
title: 數位登入 PDF 文件
linktitle: 數位登入 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 對 PDF 檔案進行數位簽章。逐步指南可確保您的文件安全且真實。
type: docs
weight: 40
url: /zh-hant/net/programming-with-security-and-signatures/digitally-sign/
---
## 介紹

在我們的數位世界中，保護文件安全的重要性怎麼強調也不為過。無論您是發送合約的自由工作者、管理發票的小型企業主還是大公司的一部分，確保您的文件保持真實且防篡改至關重要。實現這種安全性的一種有效方法是透過數位簽章。在本文中，我們將探討如何使用 Aspose.PDF for .NET 程式庫對 PDF 檔案進行數位簽署。我們將引導您一步一步完成所有事情。

## 先決條件

在深入討論細節之前，我們先確保您已具備開始對 PDF 文件進行數位簽章所需的一切。以下是先決條件清單：

1. .NET Framework：請確定您的電腦上安裝了 .NET Framework。 Aspose.PDF for .NET 支援該框架的多個版本。
2.  Aspose.PDF 庫：您需要下載並安裝 Aspose.PDF 庫。您可以從[發布連結](https://releases.aspose.com/pdf/net/).
3. 數位憑證：要簽署 PDF，您將需要一個數位憑證 —`.pfx`通常文件。
4. 開發環境：使用 Visual Studio 或您選擇的任何支援 C# 的 IDE。

一旦滿足了這些先決條件，您就可以開始簽署 PDF 文件了！

## 導入包

現在您已完成所有設置，讓我們匯入必要的套件以使我們的專案運行。在 C# 類別的頂部，包含相關的命名空間：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System.Collections;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

這些命名空間提供了您將用來透過 Aspose.PDF 操作 PDF 檔案的基本類別和方法。

## 第 1 步：設定文檔路徑

第一步是設定輸入和輸出 PDF 檔案以及數位憑證的路徑。代替`YOUR DOCUMENTS DIRECTORY`與您的系統上文件所在的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = ""; //數位憑證 (.pfx) 的路徑
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
```
在這個片段中，`inFile`是您想要簽署的原始 PDF，並且`outFile`是儲存簽名 PDF 的位置。

## 第 2 步：載入 PDF 文檔

接下來，我們需要載入我們想要簽署的PDF文件。這`Document`這裡使用Aspose.PDF中的類別：

```csharp
using (Document document = new Document(inFile))
{
    //在這裡繼續簽邏輯...
}
```

此程式碼開啟您的 PDF 檔案並為進一步操作做好準備。

## 步驟 3：初始化 PdfFileSignature 類

載入文檔後，我們建立一個實例`PdfFileSignature`類，它允許我們在加載的 PDF 文件上使用數位簽名。

```csharp
using (PdfFileSignature signature = new PdfFileSignature(document))
{
    //準備簽署流程
}
```

此類是您了解與 PDF 簽名相關的所有內容的首選！

## 步驟4：建立數位憑證實例

您可以在此處設定用於簽署 PDF 的憑證。您需要提供您的路徑`.pfx`文件以及與其關聯的密碼。

```csharp
PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
```

確保更換`"WebSales"`使用您的實際證書密碼。

## 步驟 5：設定簽名外觀

接下來，我們定義簽名在 PDF 中的顯示方式。您可以使用矩形自訂簽名的位置和外觀。 

```csharp
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
```

在這裡，我們將簽名放置在座標 (100, 100) 處，寬度為 200，高度為 100。

## 第 6 步：建立並儲存簽名

現在是時候實際建立簽名並保存簽署的 PDF 了。您可以描述簽名的原因、您的聯絡方式和地點。這可以幫助以後的驗證過程。

```csharp
DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
signature.Save(outFile);
```

## 步驟7：驗證簽名

儲存已簽署的 PDF 後，最好驗證簽名是否已正確新增。我們可以檢索簽名名稱並檢查其是否有效。 

```csharp
using (Document document = new Document(outFile))
{
    using (PdfFileSignature signature = new PdfFileSignature(document))
    {
        IList<string> sigNames = signature.GetSignNames();
        if (sigNames.Count > 0) 
        {
            if (signature.VerifySigned(sigNames[0] as string)) 
            {
                if (signature.IsCertified) 
                {
                    if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) 
                    {
                        //簽名有效且經認證
                    }
                }
            }
        }
    }
}
```

這部分確保您的工作得到驗證；畢竟，您不想發送未簽名的文件！

## 第 8 步：處理異常

將程式碼包裝在 try-catch 區塊中以優雅地處理任何異常總是明智的。 

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

這樣，如果發生意外情況，您將確切地知道出了什麼問題，而不會導致應用程式崩潰。

## 結論

數位簽名為文件提供了必要的保護，證明了真實性和完整性。使用 Aspose.PDF for .NET，簽署 PDF 檔案是一個簡單的過程，可以顯著增強您的文件管理工作流程。現在您已經了解如何將簽章數位化，您可以向客戶和合作夥伴保證您的專業和安全的文件處理。

## 常見問題解答

### 什麼是數位簽章？
數位簽章是手寫簽章的加密等效形式。它確保資料的真實性和完整性。

### 我可以在任何 .NET 應用程式中使用 Aspose.PDF 對 PDF 檔案進行簽署嗎？
是的！ Aspose.PDF for .NET 與各種 .NET 應用程式相容，包括桌面、Web 和服務。

### 我可以使用哪些類型的數位憑證？
您可以使用任何 PKCS#12 證書，通常會保存在`.pfx`或者`.p12`文件。

### 是否有 Aspose.PDF 的試用版？
是的！您可以從以下位置下載免費試用版[Aspose 發佈頁面](https://releases.aspose.com/).

### 如果遇到問題，我該如何獲得支援？
如需支持，您可以訪問[Aspose PDF 論壇](https://forum.aspose.com/c/pdf/10).