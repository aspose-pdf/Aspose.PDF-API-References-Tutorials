---
title: 使用 PDF 檔案中的文字片段旋轉文字
linktitle: 使用 PDF 檔案中的文字片段旋轉文字
second_title: Aspose.PDF for .NET API 參考
description: 透過逐步指南了解如何使用 Aspose.PDF for .NET 旋轉 PDF 檔案中的文字。探索從定位到旋轉的文字操作技術。
type: docs
weight: 390
url: /zh-hant/net/programming-with-text/rotate-text-using-text-fragment/
---
## 介紹

建立 PDF 是一回事，但如何操作它們以滿足特定要求？這才是真正的魔法發生的地方！有沒有想過如何旋轉 PDF 中的文字？無論您是產生報告還是建立具有自訂設計的文檔，旋轉文字片段都可以使您的 PDF 更具視覺吸引力。在本教程中，我們將探索如何使用 Aspose.PDF for .NET 旋轉文本，這是一個功能強大的庫，允許無縫操作 PDF 文件。

## 先決條件

在我們開始編寫程式碼之前，讓我們快速瀏覽一下您需要的工具和設定。您希望一切準備就緒，以便您可以毫不費力地進行操作。

### Aspose.PDF for .NET 函式庫
首先，您需要在專案中安裝 Aspose.PDF for .NET。該庫包含多種功能，可協助您以程式設計方式建立、修改和管理 PDF 文件。如果您還沒有下載，可以從以下位置取得：
- [下載 .NET 版 Aspose.PDF](https://releases.aspose.com/pdf/net/)

對於本教程，請確保您使用的是最新版本的庫。

### 開發環境
您還需要一個 .NET 開發環境，例如 Visual Studio。它是 C# 開發的首選 IDE，它將使您的編碼體驗流暢且有效率。

### 臨時或正式許可證
雖然您可以開始免費試用 Aspose.PDF，但如果您想避免任何限制，最好使用臨時或完整授權。您可以透過以下方式獲得：
- [免費試用](https://releases.aspose.com/)
- [臨時執照](https://purchase.aspose.com/temporary-license/)
- [購買完整許可證](https://purchase.aspose.com/buy)

準備好這些必需品後，我們就可以繼續前進了！

## 導入包

在我們開始編碼之前，您需要匯入 Aspose.PDF 附帶的必要命名空間。這對於處理文件、頁面、文字片段等至關重要。在 C# 檔案的開頭加入以下程式碼：

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

現在，讓我們逐步分解範例程式碼，以便您可以像專業人士一樣旋轉文字！

## 第 1 步：初始化文檔對象

每個 PDF 操作都從建立或載入 PDF 文件開始。在這裡，我們將使用 Aspose.PDF 從頭開始初始化新的 PDF 文件。

我們正在創建一個新的`Document`代表 PDF 檔案的對象。最初，該文檔是空的。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//初始化文檔對象
Document pdfDocument = new Document();
```

解釋：  
- `dataDir`：這是保存最終 PDF 的目錄。
- `Document pdfDocument = new Document();`：這會初始化一個新的空 PDF 文件。 

## 步驟 2：新增頁面

接下來，我們需要在文件中新增頁面。 PDF 基本上是頁面的集合，您至少需要一個頁面來新增內容。

```csharp
//取得特定頁面
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

如果不添加頁面，就沒有畫布可以繪製或放置文字！

## 第 3 步：建立第一個文字片段

現在到了令人興奮的部分！讓我們為 PDF 新增一個文字片段。文字片段是具有特定屬性（如字體、大小和位置）的一段文字。

```csharp
//建立文字片段
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```

- TextFragment(“main text”)：這將建立一個內容為「main text」的新文字片段。
- Position(100, 600)：定義文字在頁面上的位置。第一個數字是 x 座標，第二個數字是 y 座標。
- TextState.FontSize：設定文字的字體大小。
- FontRepository.FindFont：尋找要套用於文字的指定字型。

## 第 4 步：建立旋轉文字片段

讓我們添加更多文字片段，但這次我們將它們旋轉到不同的角度！

### 將文字片段旋轉 45 度

```csharp
//建立旋轉的文字片段
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
```

在這裡，關鍵的改變是：
- TextState.Rotation：此屬性設定文字片段的旋轉角度，在本例中為 45 度。

### 將文字片段旋轉 90 度

```csharp
//建立旋轉的文字片段
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

在本例中，旋轉為 90 度。

## 步驟 5：將文字片段附加到 PDF 頁面

現在我們已準備好所有文字片段，是時候使用 TextBuilder 類別將它們附加到 PDF 頁面了。

```csharp
//建立 TextBuilder 對象
TextBuilder textBuilder = new TextBuilder(pdfPage);
//將文字片段附加到 PDF 頁面
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

TextBuilder 類別有助於將多個文字片段新增至單一頁面，讓您可以靈活地單獨操作它們。

## 步驟 6：儲存 PDF 文檔

最後將文檔儲存到指定目錄。沒有這一步，你所有的努力都將化為泡影！

```csharp
//儲存文件
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

您已使用 Aspose.PDF for .NET 成功旋轉了 PDF 檔案中的文字。現在您可以打開 PDF 來查看旋轉的文字片段！

## 結論

旋轉 PDF 中的文字可以為您的文件增添專業氣息，使其具有視覺吸引力和獨特性。使用 Aspose.PDF for .NET，操作文字片段變得非常容易，讓您可以完全控制內容的顯示方式。現在您已經了解如何旋轉文本，您可以嘗試不同的角度和佈局來滿足您的專案需求。

## 常見問題解答

### 我可以以任意角度旋轉文字片段嗎？
是的！您可以設定`TextState.Rotation`屬性到任意角度（甚至負角度）以根據需要旋轉文字。

### 我可以為每個文字片段使用不同的字體嗎？
絕對地。您可以使用自訂每個文字片段的字體`FontRepository.FindFont`並傳遞您想要套用的字體。

### Aspose.PDF 支援多頁 PDF 嗎？
是的，您可以為 PDF 文件新增多個頁面並獨立操作每個頁面。

### 我可以添加的文字片段數量有限制嗎？
不，您可以根據需要添加任意數量的文字片段。只需確保它們在頁面上的位置正確即可。

### 新增文字片段後可以修改它們嗎？
是的，新增文字片段後，您仍然可以更新其屬性或將其從頁面中刪除。