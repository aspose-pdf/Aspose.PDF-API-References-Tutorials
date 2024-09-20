---
title: 在 PDF 檔案中新增文字邊框
linktitle: 在 PDF 檔案中新增文字邊框
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增文字邊框。增強您的 PDF 文件。
type: docs
weight: 70
url: /zh-hant/net/programming-with-text/add-text-border/
---
## 介紹

建立和操作 PDF 文件已成為當今數位世界的基本技能。無論您是產生報告、發票或任何其他類型的文檔，控製文字的顯示方式都會產生重大影響。您可能想要實現的此類增強功能之一是在 PDF 文件中的文字周圍添加邊框。在本指南中，我們將引導您完成使用 .NET 的 Aspose.PDF 庫在 PDF 檔案中新增文字邊框的步驟。那麼，就讓我們開始吧！

## 先決條件

在我們開始之前，您需要做好一些準備。別擔心，這非常簡單！

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。這將是您編寫和運行程式碼的開發環境。
2.  Aspose.PDF for .NET：您需要下載並安裝 Aspose.PDF 庫。您可以從[Aspose PDF for .NET 下載頁面](https://releases.aspose.com/pdf/net/) 。如果您想先嘗試一下，您還可以獲得[在這裡免費試用](https://releases.aspose.com/).
3. C# 基礎知識：對 C# 程式語言的基本了解將幫助您輕鬆理解範例。
4. .NET Framework：確保您已在專案中安裝並設定 .NET Framework。

一旦滿足了這些先決條件，您就可以開始編碼了！

## 導入包

現在我們已經完成了所有設置，讓我們匯入必要的套件以在我們的專案中使用 Aspose.PDF。您可以透過在 C# 檔案頂部新增以下 using 指令來完成此操作：

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

這些命名空間將允許您有效地處理 PDF 文件和文字片段。 

現在，讓我們將新增文字邊框的過程分解為詳細步驟。我們將詳細介紹每個步驟，以便您可以準確地了解幕後發生的情況。

## 第 1 步：設定文檔

首先，我們需要建立一個新的 PDF 文件。這就是我們所有魔法發生的地方。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立新文檔對象
Document pdfDocument = new Document();
```

在此步驟中，我們指定要儲存 PDF 檔案的目錄。然後我們建立一個新的實例`Document`類，它代表我們的 PDF 文件。

## 第 2 步：新增頁面

接下來，我們需要在文件中新增頁面。將此視為添加空白畫布，我們將在其中放置文字。

```csharp
//取得特定頁面
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

在這裡，我們稱之為`Add()`方法上的`Pages`我們的集合`pdfDocument`目的。這會為文件添加一個新頁面，並且我們將對其的引用儲存在`pdfPage`多變的。

## 第 3 步：建立文字片段

現在，讓我們建立要在 PDF 中顯示的文字。這就是我們定義文字片段內容的地方。

```csharp
//建立文字片段
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

在此程式碼中，我們建立一個新的`TextFragment`帶有文字“main text”的物件。我們還使用以下命令來設定其在頁面上的位置`Position`班級。座標 (100, 600) 指定文字在頁面上的放置位置。

## 第 4 步：設定文字屬性

接下來，我們將自訂文字片段以使其具有視覺吸引力。這包括設定字體大小、字體類型、背景顏色和前景色。

```csharp
//設定文字屬性
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

這裡，我們將字體大小設為12，使用「Times New Roman」作為字體，並套用淺灰色背景色和紅色文字。這些屬性有助於增強文字的可見性。

## 步驟5：設定邊框的描邊顏色

現在，我們進入了令人興奮的部分 - 在文字周圍添加邊框！

```csharp
//設定 StrokingColor 屬性以在文字矩形周圍繪製邊框（描邊）
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

在此步驟中，我們指定要在文字周圍繪製的邊框的顏色。在這裡，我們選擇了深紅色。

## 第 6 步：啟用文字矩形邊框

要實際繪製文字周圍的邊框，我們需要啟用`DrawTextRectangleBorder`財產。

```csharp
//將 DrawTextRectangleBorder 屬性值設為 true
textFragment.TextState.DrawTextRectangleBorder = true;
```

透過將此屬性設為`true`，我們告訴 Aspose.PDF 根據指定的描邊顏色在文字矩形周圍繪製邊框。

## 第 7 步：將文字片段附加到頁面

現在我們已經準備好文字片段並設定了所有屬性，是時候將其新增至頁面了。

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

在這裡，我們創建一個`TextBuilder`與我們相關聯的對象`pdfPage`。然後我們使用`AppendText`方法來添加我們的`textFragment`到頁面。 

## 第 8 步：儲存文檔

最後，我們需要將我們的PDF文件儲存到指定的目錄中。這是關鍵時刻！

```csharp
//儲存文件
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

在這一步中，我們稱`Save`我們的方法`pdfDocument`對象，提供我們要保存文件的路徑。運行程式碼後，您應該在指定目錄中找到新建立的帶有文字邊框的 PDF！

## 結論

現在你就擁有了！您已使用 Aspose.PDF for .NET 成功地為 PDF 檔案新增文字邊框。這個簡單而強大的功能可以顯著增強 PDF 文件的可讀性和美觀性。無論您是在建立報告、手冊或任何其他類型的文檔，了解如何操作文字格式都會派上用場。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員使用 .NET 框架以程式設計方式建立、操作和處理 PDF 文件。

### 我可以免費試用 Aspose.PDF 嗎？
是的！ Aspose 提供了[免費試用](https://releases.aspose.com/)他們的 PDF 庫，讓您在購買之前測試其功能。

### 如何購買 Aspose.PDF for .NET？
您可以直接從他們的網站購買 Aspose.PDF for .NET[購買頁面](https://purchase.aspose.com/buy).

### 是否支援 Aspose.PDF？
絕對地！您可以透過訪問獲得支持[Aspose 支援論壇](https://forum.aspose.com/c/pdf/10).

### 如果我需要臨時許可證怎麼辦？
Aspose 提供了一個[臨時執照](https://purchase.aspose.com/temporary-license/)為需要在有限時間內評估庫的開發人員提供的選項。