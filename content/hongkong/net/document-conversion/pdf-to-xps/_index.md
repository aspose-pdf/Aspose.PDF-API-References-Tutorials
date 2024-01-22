---
title: PDF 到 XPS
linktitle: PDF 到 XPS
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將 PDF 轉換為 XPS 的逐步指南。
type: docs
weight: 220
url: /zh-hant/net/document-conversion/pdf-to-xps/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 將 PDF 檔案轉換為 XPS（XML 紙張規格）格式的過程。 XPS 格式是一種基於 XML 的文件格式，用於以電子方式表示文件。透過執行以下步驟，您將能夠將 PDF 檔案轉換為 XPS 格式。

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與您的 PDF 檔案所在的實際目錄。

## 步驟 2：實例化 XPS 儲存選項
載入 PDF 檔案後，我們將實例化 XPS 儲存選項。使用以下程式碼：

```csharp
//實例化 XPS 保存選項
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## 步驟 3：儲存生成的 XPS 文件
現在我們將轉換後的 PDF 檔案儲存為 XPS 格式。使用以下程式碼：

```csharp
//儲存 XPS 文檔
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

上面的程式碼將轉換後的PDF檔案儲存為XPS格式，檔案名為`"PDFToXPS_out.xps"`.


### 使用 Aspose.PDF for .NET 將 PDF 轉換為 XPS 的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入 PDF 文件
Document pdfDocument = new Document(dataDir + "input.pdf");

//實例化 XPS 保存選項
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

//儲存 XPS 文檔
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## 結論
在本教學中，我們介紹了使用 Aspose.PDF for .NET 將 PDF 檔案轉換為 XPS 格式的逐步流程。按照上述說明操作，您現在應該能夠將 PDF 文件轉換為 XPS 格式。當您想要檢視或列印 XPS 格式的 PDF 文件時，此功能非常有用。

### 常見問題解答

#### Q：XPS格式是否適合跨平台相容？

答：XPS 格式是一種基於 XML 的檔案格式，與平台無關，可在各種作業系統和裝置上檢視。預設情況下，Windows 平台支援 XPS 文件，某些第三方應用程式和檢視器可能適用於其他平台。

#### Q：Aspose.PDF for .NET 在 XPS 轉換過程中可以處理具有多個頁面和影像的複雜 PDF 檔案嗎？

答：是的，Aspose.PDF for .NET 可以在 XPS 轉換過程中處理具有多個頁面和影像的複雜 PDF 檔案。它在將 PDF 轉換為 XPS 格式時準確保留 PDF 的佈局、圖像和文字內容。

#### Q：是否可以在 XPS 轉換過程中指定其他設定或選項？

答：是的，Aspose.PDF for .NET 提供了可以在 XPS 轉換過程中自訂的各種選項和設定。您可以使用以下命令控製圖像壓縮、字體嵌入和其他設置`XpsSaveOptions`班級。

#### Q：能否使用 Aspose.PDF for .NET 將受密碼保護的 PDF 轉換為 XPS 格式？

答：是的，Aspose.PDF for .NET 支援將受密碼保護的 PDF 轉換為 XPS 格式。載入受密碼保護的 PDF 時，您可以使用`Document`類別構造函數或透過設定`Password`載入 PDF 之前的屬性。