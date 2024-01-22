---
title: PDF 轉 SVG
linktitle: PDF 轉 SVG
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將 PDF 轉換為 SVG 的逐步指南。
type: docs
weight: 180
url: /zh-hant/net/document-conversion/pdf-to-svg/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 將 PDF 轉換為 SVG 格式的過程。 SVG（可縮放向量圖形）是一種向量影像格式，有助於維持圖形的品質和縮放比例。透過執行以下步驟，您將能夠將 PDF 檔案轉換為 SVG 格式。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：載入 PDF 文檔
在此步驟中，我們將使用 Aspose.PDF for .NET 載入來源 PDF 檔案。請按照以下程式碼操作：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與您的 PDF 檔案所在的實際目錄。

## 步驟 2：SVG 儲存選項的實例化
載入 PDF 檔案後，我們將實例化 SVG 儲存選項。使用以下程式碼：

```csharp
//實例化 SvgSaveOptions 對象
SvgSaveOptions saveOptions = new SvgSaveOptions();
//不要在 Zip 檔案中壓縮 SVG 映像
saveOptions.CompressOutputToZipArchive = false;
```

## 步驟 3：儲存生成的 SVG 文件
現在我們要將轉換後的 PDF 檔案儲存為 SVG 格式。使用以下程式碼：

```csharp
//將輸出儲存到 SVG 文件
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

上面的程式碼將轉換後的 PDF 儲存為 SVG 格式，檔案名為`"PDFToSVG_out.svg"`.

### 使用 Aspose.PDF for .NET 將 PDF 轉換為 SVG 的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
//實例化 SvgSaveOptions 對象
SvgSaveOptions saveOptions = new SvgSaveOptions();
//請勿將 SVG 映像壓縮為 Zip 檔案
saveOptions.CompressOutputToZipArchive = false;
//將輸出儲存為 SVG 文件
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## 結論
在本教學中，我們介紹了使用 Aspose.PDF for .NET 將 PDF 檔案轉換為 SVG 格式的逐步流程。按照上述說明操作，您現在應該能夠將 PDF 檔案轉換為 SVG 格式。當您希望在轉換為向量圖像時保持圖形品質和縮放比例時，此功能非常有用。

### 常見問題解答

#### Q：在 PDF 到 SVG 轉換過程中，我可以控制產生的 SVG 檔案的解析度或大小嗎？

答：是的，您可以在使用 Aspose.PDF for .NET 將 PDF 轉換為 SVG 期間控制產生的 SVG 檔案的解析度或大小。這`SvgSaveOptions`類別提供如下屬性`PageSavingCallback`和`SaveFormat`允許您設定解析度、頁面大小或與 SVG 輸出相關的其他參數。您可以根據您的要求自訂這些選項，以控制 SVG 檔案的品質和大小。

#### Q：Aspose.PDF for .NET 是否支援將加密或受密碼保護的 PDF 轉換為 SVG？

答：是的，Aspose.PDF for .NET 支援將加密或受密碼保護的 PDF 轉換為 SVG 格式。當您載入受密碼保護的 PDF 時，您可以使用`Document`類別構造函數或透過設定`Password`載入 PDF 之前的屬性。 Aspose.PDF for .NET 將在 PDF 到 SVG 轉換過程中處理解密。

#### Q：我可以只將 PDF 的特定頁面而不是整個文件轉換為 SVG 嗎？

答：是的，您可以使用 Aspose.PDF for .NET 僅將 PDF 的特定頁面轉換為 SVG，而不是整個文件。在將輸出儲存為 SVG 檔案之前，您可以透過指定頁碼或範圍來選擇要轉換的頁面。這樣，您可以僅提取所需的頁面並將其從 PDF 轉換為 SVG 格式。

#### Q：Aspose.PDF for .NET 是否與所有版本的 SVG 相容？

答：Aspose.PDF for .NET 旨在與 SVG 1.1（可縮放向量圖）規格相容。它支援根據SVG 1.1標準產生SVG檔。但請注意，SVG 2.0 已作為 SVG 規範的最新版本引入。雖然 Aspose.PDF for .NET 在許多情況下仍可與 SVG 2.0 配合良好，但建議檢查您打算使用的特定 SVG 功能的兼容性和潛在限制。