---
title: 取得 SVG 尺寸
linktitle: 取得 SVG 尺寸
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 將 SVG 檔案轉換為 PDF。非常適合想要操作 PDF 的開發人員。
type: docs
weight: 40
url: /zh-hant/net/document-conversion/get-svg-dimensions/
---
## 介紹

歡迎來到 Aspose.PDF for .NET 的世界！如果您希望以程式方式操作 PDF 文件，那麼您來對地方了。 Aspose.PDF 是一個功能強大的程式庫，可讓開發人員輕鬆建立、編輯和轉換 PDF 文件。無論您是經驗豐富的開發人員還是新手，本指南都將引導您了解使用 Aspose.PDF for .NET 的基本知識，重點介紹如何取得 SVG 尺寸並將其轉換為 PDF 格式。

## 先決條件

在我們開始編寫程式碼之前，您需要做好以下幾件事：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。這是我們將在本教程中使用的 IDE。
2.  .NET Framework：確保您已安裝 .NET Framework。 Aspose.PDF支援各種版本，所以請檢查[文件](https://reference.aspose.com/pdf/net/)為了相容性。
3.  Aspose.PDF 庫：您可以從以下位置下載最新版本的 Aspose.PDF for .NET[下載連結](https://releases.aspose.com/pdf/net/) 。如果您想先嘗試一下，您還可以獲得[免費試用](https://releases.aspose.com/).
4. 基本 C# 知識：熟悉 C# 程式設計將有助於您更好地理解範例。

## 導入包

首先，您需要匯入必要的套件。您可以這樣做：

1. 開啟您的 Visual Studio 專案。
2. 在解決方案資源管理器中以滑鼠右鍵按一下您的項目，然後選擇「管理 NuGet 套件」。
3. 搜尋“Aspose.PDF”並安裝該套件。

安裝軟體包後，您就可以開始編碼了！

## 第 1 步：設定您的項目

### 建立一個新項目

首先，讓我們在 Visual Studio 中建立一個新的 C# 專案。

- 開啟 Visual Studio 並選擇「建立新專案」。
- 選擇“控制台應用程式（.NET Framework）”，然後按一下“下一步”。
- 為您的項目命名（例如“AsposePDFExample”）並點擊“建立”。

### 新增使用指令

現在您的專案已設定完畢，您需要在專案頂部新增必要的 using 指令`Program.cs`文件：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

這將允許您存取 Aspose.PDF 庫提供的類別和方法。

## 第 2 步：載入 SVG 文檔

### 定義文檔目錄

在載入 SVG 文件之前，您需要指定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與 SVG 檔案所在的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### 載入 SVG 文檔

現在，讓我們使用以下命令加載 SVG 文檔`SvgLoadOptions`班級。此類別可讓您根據 SVG 內容調整頁面大小。

```csharp
var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

## 步驟 3：調整頁邊距

為了確保 SVG 內容完美適合 PDF，您需要將頁邊距設為零。此步驟對於保持 SVG 尺寸的完整性至關重要。

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

## 步驟 4：將文件另存為 PDF

最後，是時候將 SVG 文件另存為 PDF 了。您可以指定輸出檔名和路徑，如下所示：

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

就是這樣！您已使用 Aspose.PDF for .NET 成功將 SVG 檔案轉換為 PDF。

## 結論

恭喜！您剛剛使用 Aspose.PDF for .NET 完成了一項簡單但功能強大的任務。透過遵循本指南，您已了解如何載入 SVG 文件、調整其邊距以及將其另存為 PDF。 Aspose.PDF 的可能性是無限的，這只是冰山一角。無論您是想建立複雜的 PDF、操作現有 PDF，或是在格式之間進行轉換，Aspose.PDF 都能滿足您的需求。那麼，你還在等什麼？深入了解[文件](https://reference.aspose.com/pdf/net/)並探索該庫提供的所有功能！

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員以程式設計方式建立、編輯和轉換 PDF 文件。

### 如何安裝 Aspose.PDF？
您可以透過 Visual Studio 中的 NuGet 套件管理器安裝 Aspose.PDF 或從[地點](https://releases.aspose.com/pdf/net/).

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供了[免費試用](https://releases.aspose.com/)供您在購買前測試該庫。

### 在哪裡可以找到對 Aspose.PDF 的支援？
您可以從以下方面獲得支持[Aspose論壇](https://forum.aspose.com/c/pdf/10).

### 如何取得 Aspose.PDF 的臨時授權？
您可以請求[臨時執照](https://purchase.aspose.com/temporary-license/)來自 Aspose 網站。