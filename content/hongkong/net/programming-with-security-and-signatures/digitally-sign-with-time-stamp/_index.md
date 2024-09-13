---
title: 在 PDF 檔案中使用時間戳進行數位簽名
linktitle: 在 PDF 檔案中使用時間戳進行數位簽名
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 對帶有時間戳記的 PDF 進行數位簽章。本逐步指南涵蓋先決條件、證書設定、時間戳記等。
type: docs
weight: 50
url: /zh-hant/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## 介紹

您是否曾經需要對 PDF 進行數位簽名並包含時間戳以提高安全性？無論您正在處理法律文件、合約或任何需要安全身份驗證的內容，帶有時間戳記的數位簽名都會增加額外的可信度。在本教學中，我們將詳細介紹如何使用 Aspose.PDF for .NET 在 PDF 文件中新增數位簽章和時間戳記。別擔心，我們會一步一步來的！

## 先決條件

在我們深入研究程式碼之前，您需要設定一些內容才能繼續進行。以下是入門先決條件的快速清單：

-  Aspose.PDF for .NET 函式庫：您需要在專案中安裝 Aspose.PDF for .NET 函式庫。你可以[在這裡下載最新版本](https://releases.aspose.com/pdf/net/)或透過 NuGet 將其新增至您的專案。
- PDF 文件：您需要一個範例 PDF 文件才能使用。確保您的專案目錄中有一個要簽署的檔案。
- 數位憑證（PFX 檔案）：確保您擁有數位憑證（a`.pfx`文件）對文件進行數位簽章。
- 時間戳 URL：這是一個線上時間戳服務，用於將時間戳附加到數位簽章。 
- 基本 C# 知識：您不需要成為專家，但了解 C# 基礎知識將幫助您理解和自訂程式碼。

勾選所有這些方塊後，您就可以開始編碼了！

## 導入包

首先，您需要將以下命名空間匯入到您的 C# 專案中。這可確保您可以存取相關的 Aspose.PDF 類別和函數。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## 第 1 步：載入 PDF 文檔

我們需要做的第一件事是載入我們想要簽署的 PDF 文件。操作方法如下：

```csharp
//定義文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入 PDF 文件
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

這一步非常簡單。我們只是定義我們想要簽署的文檔的路徑。這`Document`Aspose.PDF 中的類別處理載入檔。

## 第 2 步：設定數位簽名

接下來，我們將使用 PKCS7 類別建立數位簽章並載入 PFX 檔案。此 PFX 檔案包含您的憑證和私鑰，這是簽署文件所必需的。

```csharp
// .pfx 檔案的路徑
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

//初始化簽名對象
PdfFileSignature signature = new PdfFileSignature(document);

//使用密碼載入 PFX 文件
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

此時，您告訴 Aspose 使用您的數位憑證來簽署文件。這`PKCS7`object 為您處理所有加密工作，因此您不必擔心具體細節。

## 步驟 3：新增時間戳設置

可靠的數位簽章的關鍵組成部分之一是時間戳。這確保了即使在證書過期後也可以驗證文件的簽名。讓我們使用線上時間戳權威機構來設定時間戳。

```csharp
//定義時間戳設置
TimestampSettings timestampSettings = new TimestampSettings("https://your_timestamp_url", "使用者:密碼");

//將時間戳記設定新增至 PKCS7 對象
pkcs.TimestampSettings = timestampSettings;
```

在這裡，您指定時間戳服務的 URL，該服務將自動為您的簽名提供時間和日期。這可以在有或沒有身份驗證的情況下完成。

## 第 4 步：定義簽名位置和外觀

現在，我們將定義簽名在 PDF 中的顯示位置及其尺寸。您可以自訂簽名框在頁面上的位置以及大小。

```csharp
//定義簽名外觀和位置（第 1 頁，具有指定矩形）
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

在這裡，我們定義一個矩形，將簽名放置在 PDF 第一頁上的座標 (100, 100) 處，寬度為 200，高度為 100。

## 第 5 步：簽署 PDF 文檔

一切設定完畢後，就可以將數位簽章實際套用到 PDF 了。此步驟將證書、時間戳記和定位合併到一個簡單的命令中。

```csharp
//在第一頁簽署文件
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

這是發生的事情：
- 1：這表示簽名應套用於第一頁。
- 「簽名原因」：您可以在此指定簽署文件的原因。
- 「聯絡方式」：填寫簽名人的聯絡方式。
- 「地點」：指定簽名者的地點。
- true：此佈林值指示簽名在文件中是否可見。
- rect：我們先前定義的矩形指定了簽章的大小和位置。
- pkcs：PKCS7 物件包含數位憑證和時間戳記設定。

## 第 6 步：儲存簽署的 PDF

文件簽署後，剩下要做的就是保存它。您可以選擇新的檔案名稱來保留原始版本和簽章版本。

```csharp
//儲存已簽署的 PDF 文檔
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

您新簽名並加蓋時間戳記的 PDF 現已儲存到指定目錄！

## 結論

現在你就得到它了！您已使用 Aspose.PDF for .NET 成功地對帶有時間戳記的 PDF 進行了數位簽署。此流程可確保您的文件的真實性和完整性，讓您和收件人都安心。數位簽名在當今的數位世界中變得越來越重要，因此掌握這個過程絕對是一項值得擁有的技能。

## 常見問題解答

### 我可以為憑證使用不同的文件格式嗎？  
是的，但本教學重點介紹如何使用 PFX 文件，這是數位憑證最常見的格式。

### 我需要網路連線才能套用時間戳記嗎？  
是的，由於時間戳是從線上時間戳權威機構獲取的，因此您將需要訪問互聯網。

### 我可以簽署 PDF 中的多個頁面嗎？  
絕對地！您可以修改`signature.Sign()`方法定位多個頁面或循環遍歷所有頁面。

### 如果 PFX 檔案密碼不正確會發生什麼情況？  
如果密碼錯誤，您將收到異常，因此請確保輸入正確。

### 可以讓簽名不可見嗎？  
是的，你可以透過`false`到`Sign`方法的可見性參數使簽名不可見。