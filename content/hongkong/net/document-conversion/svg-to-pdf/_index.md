---
title: SVG 轉 PDF
linktitle: SVG 轉 PDF
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆快速地將 SVG 轉換為 PDF。
type: docs
weight: 280
url: /zh-hant/net/document-conversion/svg-to-pdf/
---
本教學將引導您完成使用 Aspose.PDF for .NET 將 SVG 檔案轉換為 PDF 檔案的步驟。 Aspose.PDF 提供了一個簡單有效的解決方案，可將 SVG 檔案轉換為 PDF，同時保留內容品質和佈局。請按照以下步驟執行此轉換。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：載入 SVG 文件
第一步是將 SVG 檔案載入到`Document`使用 SVG 載入選項的物件（`SvgLoadOptions`）。使用以下程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用 SVG 載入選項實例化 LoadOption 對象
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

//建立文檔對象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與 SVG 檔案所在的實際目錄。

## 第 2 步：轉換為 PDF
第二步是使用以下命令將 SVG 文檔轉換為 PDF 文檔`Save`的方法`Document`目的。使用以下程式碼：

```csharp
//儲存生成的 PDF 文檔
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

請務必為產生的 PDF 檔案指定所需的路徑和檔案名稱。

### 使用 Aspose.PDF for .NET 將 SVG 轉換為 PDF 的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//使用 SVG 載入選項實例化 LoadOption 對象
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

//建立文檔對象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

//儲存生成的 PDF 文檔
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 將 SVG 檔案轉換為 PDF 檔案。按照上面給出的步驟，您可以輕鬆地執行此轉換。使用此方法將 SVG 檔案轉換為 PDF，並享受 Aspose.PDF 的靈活性和品質。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 C# 應用程式中處理 PDF 文件。它提供各種功能，包括將 SVG 檔案轉換為 PDF。

#### Q：為什麼我要將 SVG 檔案轉換為 PDF？

答：SVG（可縮放向量圖形）檔案通常用於網路上的向量圖形。將 SVG 檔案轉換為 PDF 格式可以更輕鬆地分享、列印和嵌入圖形內容。

#### Q：如何載入 SVG 檔案並使用 Aspose.PDF for .NET 將其轉換為 PDF？

答：要載入 SVG 文件，您可以使用`SvgLoadOptions`類別來指定 SVG 載入選項。然後，創建一個`Document`物件並將 SVG 檔案載入到其中。最後，使用`Save`的方法`Document`物件將 SVG 轉換並儲存為 PDF。

#### Q：我可以在轉換過程中自訂輸出 PDF 嗎？

答：是的，您可以在轉換過程中自訂輸出 PDF。 Aspose.PDF for .NET 提供了各種選項和屬性來控制 PDF 文件的外觀和佈局。

#### Q：產生的 PDF 中是否保留了 SVG 的內容品質？

答：是的，Aspose.PDF for .NET 可確保在 SVG 到 PDF 轉換期間保留內容品質和佈局，從而確保格式之間的無縫轉換。