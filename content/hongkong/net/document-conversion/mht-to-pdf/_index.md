---
title: MHT 轉 PDF
linktitle: MHT 轉 PDF
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將 MHT 轉換為 PDF 的逐步指南。
type: docs
weight: 70
url: /zh-hant/net/document-conversion/mht-to-pdf/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 將 MHT 檔案轉換為 PDF 的過程。 MHT（MIME HTML）是一種用於保存完整網頁的格式，包括圖像和相關內容。按照以下步驟，您將能夠將 MHT 檔案轉換為 PDF 格式。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 步驟1：載入MHT文件
在此步驟中，我們將使用 Aspose.PDF for .NET 載入 MHT 檔案。請按照以下程式碼操作：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

//載入文檔
Document document = new Document(dataDir + "test.mht", options);
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與 MHT 檔案所在的實際目錄。

## 步驟 2: MHT 到 PDF 轉換
載入MHT檔案後，我們可以繼續轉換為PDF。使用以下程式碼：

```csharp
//將輸出另存為 PDF 文檔
document.Save(dataDir + "MHTToPDF_out.pdf");
```

上面的程式碼將MHT檔案轉換為PDF格式並將其另存為檔案名`"MHTToPDF_out.pdf"`.

### 使用 Aspose.PDF for .NET 將 MHT 轉換為 PDF 的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
//載入文檔
Document document = new Document(dataDir  + "test.mht", options);
//將輸出另存為 PDF 文檔
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## 結論
在本教學中，我們介紹了使用 Aspose.PDF for .NET 將 MHT 檔案轉換為 PDF 的逐步流程。按照上述說明操作，您現在應該能夠將 MHT 檔案轉換為 PDF 格式。當您需要將整個網頁轉換為 PDF 文件時，此功能非常有用。

### 常見問題解答

#### Q：Aspose.PDF for .NET 支援將嵌入影像的 MHT 檔案轉換為 PDF 嗎？

答：是的，Aspose.PDF for .NET 支援將嵌入影像的 MHT 檔案轉換為 PDF。該庫可以處理完整的網頁內容，包括圖像和相關資源，並將其轉換為 PDF 文件。

#### Q：我可以在 MHT 轉換到 PDF 過程中自訂 PDF 輸出嗎？

答：是的，Aspose.PDF for .NET 提供了各種選項來在 MHT 到 PDF 轉換過程中自訂 PDF 輸出。您可以設定頁面大小、方向、邊距等屬性來控制產生的 PDF 文件的外觀。

#### Q：Aspose.PDF for .NET 是否會在 PDF 輸出中保留原始 MHT 檔案的超連結和格式？

答：是的，Aspose.PDF for .NET 會在 PDF 輸出中保留原始 MHT 檔案的超連結和格式。該庫確保轉換後的 PDF 保留與來源 MHT 檔案相同的佈局和內容。

#### Q：我可以使用 Aspose.PDF for .NET 將多個 MHT 檔案轉換為單獨的 PDF 文件嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將多個 MHT 檔案轉換為單獨的 PDF 文件。只需載入每個 MHT 檔案並將其儲存為具有唯一檔案名稱的單獨 PDF 文件即可。