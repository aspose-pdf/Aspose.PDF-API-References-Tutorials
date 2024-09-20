---
title: 在 PDF 檔案中新增文字印記
linktitle: 在 PDF 檔案中新增文字印記
second_title: Aspose.PDF for .NET API 參考
description: 透過我們的逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增文字圖章，並提升您的文件簡報效果。
type: docs
weight: 50
url: /zh-hant/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## 介紹

在當今的數位時代，PDF 是共享和交付文件的常見格式。無論您是開發人員、內容創建者，還是只是希望增強 PDF 文件的人，了解如何以程式設計方式操作 PDF 都可以改變遊戲規則。您可能想要利用的實用功能是在 PDF 檔案中新增文字圖章。添加文字印記可以為您的文件帶來專業感或傳達重要訊息，例如「樣本」、「機密」甚至浮水印。

## 先決條件

在我們開始編寫程式碼之前，有一些先決條件可以確保您已正確設定所有內容。這是您需要的：

1.  Aspose.PDF for .NET：請確定您的專案中已安裝了 Aspose.PDF 庫。如果您還沒有這樣做，您可以從[阿斯普斯網站](https://releases.aspose.com/pdf/net/).
2. Visual Studio 或相容 IDE：您將需要一個開發環境來編寫和執行 .NET 程式碼。 Visual Studio 是開發人員最常見的選擇。
3. C#基礎知識：熟悉C#和物件導向程式設計原理將有助於您更好地理解範例。
4. 範例 PDF 檔案：您應該有一個可供使用的 PDF 檔案。您可以建立基本 PDF 或使用任何現有 PDF 來測試功能。

一旦解決了這些先決條件，我們就可以繼續編碼了！

## 導入包

現在，讓我們導入必要的套件。此步驟至關重要，因為它使 Aspose 庫中的類別和方法在您的專案中可用。

### 匯入 Aspose.PDF 程式集

首先，您需要匯入 Aspose.PDF 命名空間。在 C# 檔案的頂部，加入以下 using 指令：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

這將使您能夠存取建立和操作 PDF 文件所必需的類別。

現在，讓我們進入本教學的重點。我們將把這個過程分解為清晰簡潔的步驟。每個步驟將指導您完成程式碼以將文字圖章新增至 PDF 檔案。

## 第 1 步：設定文檔目錄

首先，您需要建立 PDF 文件的儲存目錄。這意味著您的程式碼需要知道在哪裡可以找到您要編輯的 PDF 檔案。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

說明： 替換`"YOUR DOCUMENT DIRECTORY"`與您的 PDF 檔案的實際路徑（`AddTextStamp.pdf`) 被儲存。該路徑稍後用於開啟和儲存修改後的 PDF。

## 第 2 步：開啟 PDF 文檔

接下來，我們將使用以下命令開啟 PDF 文檔`Document`來自 Aspose.PDF 命名空間的類別。

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

說明：在這裡，我們正在建立一個實例`Document`類別並傳遞我們的 PDF 文件的路徑。這將加載 PDF，以便我們可以對其進行操作。

## 第 3 步：建立文字圖章

現在，我們將建立一個文字圖章，稍後將其套用到 PDF 文件。

```csharp
//建立文字印章
TextStamp textStamp = new TextStamp("Sample Stamp");
```

解釋：`TextStamp`物件是用您要顯示的文字建立的。在本例中，我們使用「樣本圖章」作為圖章的文字。

## 步驟 4：設定圖章屬性

要自訂您的印章，我們可以設定各種屬性，例如背景顏色、位置和旋轉。讓我們現在就這樣做：

```csharp
//設定圖章是否為背景
textStamp.Background = true;

//設定原點
textStamp.XIndent = 100;
textStamp.YIndent = 100;

//旋轉圖章
textStamp.Rotate = Rotation.on90;
```

解釋：
- 背景：將其設定為`true`表示圖章將出現在 PDF 內容的後面。
- XIndent 和 YIndent：這些屬性決定圖章在頁面上的位置。在此範例中，圖章將放置在距離頁面左邊緣和上緣 100 個單位的位置。
- 旋轉：將圖章旋轉 90 度。您可以根據您的設計要求選擇不同的旋轉選項。

## 第 5 步：自訂文字屬性

接下來，讓我們透過自訂圖章中文字的外觀來發揮創意：

```csharp
//設定文字屬性
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

解釋：
- 字體：我們使用 Arial 字體並將其設定為粗體和斜體。
- FontSize：設定為14磅。
- ForegroundColor：使用 RGB 將文字顏色設定為 Aqua。請隨意更改顏色以滿足您的品牌或設計需求！

## 第 6 步：將圖章新增至 PDF 頁面

現在是時候將圖章新增至 PDF 文件的特定頁面了。

```csharp
//新增圖章到特定頁面
pdfDocument.Pages[1].AddStamp(textStamp);
```

說明： 在此範例中，圖章被加入到 PDF 的第一頁（頁為 1 索引）。根據文檔的需要調整頁碼。

## 第7步：儲存修改後的PDF

最後，讓我們儲存帶有新新增的文字圖章的文件。

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

//儲存輸出文檔
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

說明：我們為輸出檔案定義一個新路徑，然後儲存修改後的文件。儲存後，路徑印到控制台，確認操作成功。

## 結論

恭喜！您已使用 Aspose.PDF for .NET 成功將文字圖章新增至 PDF 檔案。這種方法可以讓您有效地對文件進行註釋，從而提高其專業性和可用性。無論您是添加浮水印、簽名還是簡單的註釋，Aspose 庫都提供了強大的工具來輕鬆操作您的 PDF。

## 常見問題解答

### 什麼是 PDF 中的文字印記？
文字圖章是包含可放置在 PDF 文件上的文字的圖形疊加層，通常用於註釋或浮水印。

### 我可以用圖像訂製印章嗎？
是的，Aspose.PDF 也支援新增圖像圖章，提供更多的設計彈性。

### 我可以在 Aspose.PDF 中使用哪些程式語言？
Aspose.PDF 主要專注於 .NET，但也有適用於其他語言（例如 Java 和 Python）的版本。

### 如何取得 Aspose.PDF 的臨時授權？
您可以造訪以下網站申請臨時許可證[購買連結](https://purchase.aspose.com/temporary-license/)在他們的網站上。

### 在哪裡可以找到對 Aspose.PDF 的支援？
對 Aspose.PDF 的支援可在其網站上找到[支援論壇](https://forum.aspose.com/c/pdf/10).