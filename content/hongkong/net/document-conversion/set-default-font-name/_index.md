---
title: 設定預設字體名稱
linktitle: 設定預設字體名稱
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將 PDF 渲染為圖像時設定預設字體名稱。本指南涵蓋先決條件、逐步說明和常見問題。
type: docs
weight: 270
url: /zh-hant/net/document-conversion/set-default-font-name/
---
## 介紹

您是否曾嘗試將 PDF 文件渲染為圖像，但發現字體看起來不正確？也許文字出現扭曲，或者原始字體不受支援。這就是設定預設字體可以挽救局面的地方！使用 Aspose.PDF for .NET，您可以輕鬆為 PDF 渲染設定預設字體，確保您的文件看起來清晰且專業。在本教程中，我們將引導您了解如何在將 PDF 渲染為圖像時設定預設字體名稱。閱讀本指南後，您將掌握解決遇到的任何 PDF 渲染挑戰的技能。準備好？讓我們深入了解吧！

## 先決條件

在我們開始編寫程式碼之前，您需要做好以下幾件事：

- Aspose.PDF for .NET：我們將使用這個強大的程式庫來操作 PDF 文件。您可以從[阿斯普斯網站](https://releases.aspose.com/pdf/net/).
- Visual Studio：確保您的電腦上安裝了 Visual Studio。這將是我們的開發環境。
- .NET Framework：確保您已安裝 .NET Framework。 Aspose.PDF for .NET 支援各種版本，因此請檢查文件以符合您的需求。
- PDF 文件：您需要一個範例 PDF 文件才能使用。如果您沒有，請建立一個簡單的 PDF 或線上下載範例。

一切準備就緒後，我們就可以開始編碼了！

## 導入包

在我們深入研究程式碼之前，必須導入必要的套件。這確保了我們可以存取項目所需的所有類別和方法。

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

這些匯入至關重要，因為它們引入了處理 PDF 操作、影像渲染和檔案流操作所需的命名空間。

## 第 1 步：設定您的專案和文件路徑

首先，讓我們設定 PDF 文件所在的目錄路徑。這將是您操作 PDF 文件的起點。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
這裡，`dataDir`是 PDF 文件所在的目錄。確保更換`"YOUR DOCUMENT DIRECTORY"`與文檔的實際路徑。這很重要，因為程式碼需要知道從哪裡取得 PDF 檔案。

## 第 2 步：載入 PDF 文檔

現在我們已經有了文件路徑，下一步是將 PDF 文件載入到記憶體中，以便我們可以開始處理它。

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
我們使用`Document`Aspose.PDF 庫中的類別來載入我們的 PDF 檔案。此類別提供了處理 PDF 文件的各種方法和屬性。這`"input.pdf"`應替換為 PDF 的實際檔名。該檔案將用作渲染的輸入。

## 步驟 3：為輸出建立影像流

載入文件後，我們需要設定一個流來保存渲染的圖像。這是儲存輸出影像的位置。

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
這`FileStream`類別用於建立一個新文件，其中將保存渲染的圖像。在此範例中，我們將圖像另存為`"SetDefaultFontName.png"` 。這`FileMode.Create`確保建立新文件或覆蓋現有文件。

## 步驟 4：設定影像的分辨率

在將 PDF 渲染為圖像之前，設定解析度至關重要。這決定了輸出影像的品質和清晰度。

```csharp
Resolution resolution = new Resolution(300);
```
這`Resolution`類別設定輸出影像的解析度。在這裡，我們選擇了 300 DPI（每英寸點數）的分辨率，這是高品質影像的標準。這可確保 PDF 中的文字和圖形清晰呈現，而不會失去細節。

## 第5步：配置PNG設備

接下來，我們需要配置處理 PDF 到 PNG 影像渲染的裝置。

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
這`PngDevice`類別負責將 PDF 文件渲染為 PNG 影像。透過透過`resolution`反對它，我們確保圖像是使用指定的 DPI 創建的。

## 步驟 6：設定預設字體名稱

這是關鍵部分——設定預設字體名稱。如果 PDF 中的原始字體不可用，這將是後備字體。

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
我們建立一個實例`RenderingOptions`並設定其`DefaultFontName`財產給`"Arial"`。這意味著如果無法找到 PDF 中的原始字體，將使用 Arial 代替。此步驟對於保持渲染圖像中文字的可讀性和外觀至關重要。

## 第 7 步：將 PDF 頁面渲染為圖像

最後，一切設定完畢後，我們現在可以將 PDF 文件的第一頁渲染為圖像，並使用我們先前建立的文件流來保存它。

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
這`Process`的方法`PngDevice`類別用於將指定的 PDF 頁面（在本例中為第一頁）渲染為圖像。然後輸出保存到`imageStream`。此步驟將 PDF 頁面轉換為具有指定解析度和預設字體的 PNG 圖像。

## 步驟8：關閉文件流程和PDF文檔

渲染圖像後，必須關閉文件流和 PDF 文件以釋放資源。

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
關閉`imageStream`確保檔案正確保存並且沒有資料遺失。處置`pdfDocument`釋放記憶體和資源，防止任何潛在的記憶體洩漏。

## 結論

現在你就得到它了！只需幾行程式碼，您就學會如何在使用 Aspose.PDF for .NET 將 PDF 渲染為圖像時設定預設字體名稱。這項技能非常方便，尤其是在處理可能包含不支援的字體的 PDF 時。透過設定預設字體，您可以確保渲染的圖像保持其可讀性和專業外觀。

## 常見問題解答

### 如果系統上未安裝指定的預設字型會發生什麼情況？
如果在中指定的預設字體`RenderingOptions`如果系統上未安裝，Aspose.PDF 將使用系統定義的後備字體。

### 我可以使用 Arial 以外的字體作為預設字體嗎？
絕對地！您可以將系統上安裝的任何字體設定為預設字體。

### 是否可以一次將 PDF 的多頁渲染為影像？
是的，您可以循環瀏覽 PDF 的頁面並使用相同的流程單獨渲染每個頁面。

### 設定高解析度是否會影響 PDF 渲染的效能？
是的，更高的解析度會產生更大的圖像文件，並且可能會增加渲染時間，但它們也會產生更清晰的圖像。

### 我可以將 PDF 渲染為 PNG 以外的其他圖像格式嗎？
是的，Aspose.PDF 支援渲染為各種影像格式，例如 JPEG、BMP 和 TIFF。