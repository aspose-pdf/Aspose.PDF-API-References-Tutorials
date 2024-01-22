---
title: 取得 SVG 尺寸
linktitle: 取得 SVG 尺寸
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 取得 SVG 尺寸的逐步指南。
type: docs
weight: 40
url: /zh-hant/net/document-conversion/get-svg-dimensions/
---
## 介紹
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 取得 SVG 檔案尺寸的過程。 SVG（可縮放向量圖形）是一種基於 XML 的圖像格式，用於表示向量圖形。使用以下步驟，您將能夠取得 SVG 檔案的尺寸並將其另存為 PDF。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：載入 SVG 文件
在此步驟中，我們將使用 Aspose.PDF for .NET 載入 SVG 檔案。請按照以下程式碼操作：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與 SVG 檔案所在的實際目錄。

## 步驟2：頁面大小調整
現在我們已經載入了 SVG 文件，我們可以調整頁面大小以適應 SVG 內容。使用以下程式碼：

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

上面的程式碼將頁邊距設為零，允許根據 SVG 內容調整頁面大小。

## 步驟 3： 儲存產生的 PDF
調整頁面大小後，我們現在可以儲存產生的PDF文件。這是最後一步：

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

代替`"YOUR DOCUMENTS DIRECTORY"`以及要儲存輸出 PDF 檔案的所需目錄。
  
### 使用 Aspose.PDF for .NET 取得 SVG 尺寸的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## 結論
在本教學中，我們介紹了使用 Aspose.PDF for .NET 取得 SVG 檔案尺寸的逐步流程。按照上述說明操作，您現在應該能夠取得 SVG 檔案的尺寸並將其儲存為 PDF 格式。當您需要測量向量圖形的尺寸時，此功能非常有用。

### 常見問題解答

#### Q：什麼是 SVG？

答：SVG（可縮放向量圖形）是一種基於 XML 的圖像格式，用於表示向量圖形。與光柵影像不同，SVG 檔案與解析度無關，並且可以在不損失品質的情況下進行縮放。 SVG 廣泛用於在網路上顯示圖形，並且可以輕鬆編輯和操作。

#### Q：為什麼要使用 Aspose.PDF for .NET 進行 SVG 到 PDF 的轉換？

答：Aspose.PDF for .NET 提供了一個可靠且有效率的方法來處理 SVG 檔案並將其轉換為 PDF 格式。它提供了各種選項和設定來自訂轉換過程，例如調整頁面大小、邊距和其他屬性，以確保 PDF 中的準確表示。

#### Q：我可以轉換具有複雜圖形和文字的 SVG 檔案嗎？

答：是的，Aspose.PDF for .NET 可以處理具有複雜圖形、文字和向量元素的 SVG 檔案。它在轉換過程中準確保留 SVG 內容的細節和質量，從而產生高品質的 PDF 文件。

#### Q：是否可以使用 Aspose.PDF for .NET 從 SVG 檔案中擷取文字？

答：是的，Aspose.PDF for .NET 允許您從 SVG 檔案中提取文字。您可以使用該庫的文本提取功能從 SVG 中提取文字元素並單獨保存以供進一步處理。