---
title: PDF 轉 PDFA3b
linktitle: PDF 轉 PDFA3b
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將 PDF 轉換為 PDF/A-3b 的逐步指南。
type: docs
weight: 150
url: /zh-hant/net/document-conversion/pdf-to-pdfa3b/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 將 PDF 檔案轉換為 PDF/A-3b 格式的過程。 PDF/A-3b 是用於在 PDF 文件中嵌入文件和資料的 ISO 標準。請依照以下步驟，您將能夠將 PDF 檔案轉換為 PDF/A-3b 格式。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：開啟來源 PDF 文檔
在此步驟中，我們將使用 Aspose.PDF for .NET 開啟來源 PDF 檔案。請按照以下程式碼操作：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//開啟來源PDF文檔
Document pdfDocument = new Document(dataDir + "input.pdf");
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與您的 PDF 檔案所在的實際目錄。

## 第 2 步：轉換為 PDF/A-3b
開啟PDF檔案後，我們可以繼續轉換為PDF/A-3b格式。使用以下程式碼：

```csharp
//轉換為 PDF/A-3b 格式
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

上面的程式碼將 PDF 文件轉換為 PDF/A-3b 格式並消除任何轉換錯誤。

## 步驟 3：儲存產生的 PDF/A-3b 文件
轉換完成後，我們需要儲存產生的PDF/A-3b檔案。這是最後一步：

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
//儲存輸出文檔
pdfDocument.Save(dataDir);
```

代替`"YOUR DOCUMENTS DIRECTORY"`以及要儲存輸出 PDF/A-3b 檔案的所需目錄。

### 使用 Aspose.PDF for .NET 將 PDF 轉換為 PDFA3b 的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
//儲存輸出文檔
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## 結論
在本教學中，我們介紹了使用 Aspose.PDF for .NET 將 PDF 檔案轉換為 PDF/A-3b 格式的逐步流程。按照上述說明操作，您現在應該能夠將 PDF 文件轉換為 PDF/A-3b 格式。當您想要將其他文件和資料嵌入到符合 PDF/A-3b 標準的 PDF 文件中時，此功能非常有用。

### 常見問題解答

#### Q：什麼是 PDF/A-3b，它與其他 PDF/A 標準有何不同？

答：PDF/A-3b 是一項 ISO 標準，允許將文件和資料嵌入 PDF 文件中，使其獨立並確保長期保存。與其他 PDF/A 標準（例如 PDF/A-1 和 PDF/A-2）不同，PDF/A-3b 允許在 PDF 文件中包含其他文件和資料。此功能使其適合歸檔和交換複雜的互動式文件。

#### Q：我可以在 PDF/A-3b 文件中包含多個文件和資料嗎？

答：是的，PDF/A-3b 的主要優點之一是它能夠在 PDF 文件中包含多個文件和資料。您可以嵌入各種類型的文件，例如 XML、電子表格、圖像或其他 PDF 文件以及主要 PDF 內容。因此，PDF/A-3b 文件成為包含所有必要元素的獨立套件。

#### Q：如果 PDF 到 PDF/A-3b 轉換過程中出現錯誤，會發生什麼事？

答：使用 Aspose.PDF for .NET 將 PDF 轉換為 PDF/A-3b 格式時，您可以控制錯誤的處理方式。這`Convert`方法`ConvertErrorAction`參數決定遇到錯誤時要採取的動作。在提供的程式碼範例中，`ConvertErrorAction.Delete`使用參數，這意味著轉換過程中遇到任何錯誤都會導致刪除有錯誤的頁面。

#### Q：PDF/A-3b 適合長期保存文件嗎？

答：是的，PDF/A-3b 是專門為長期保存電子文檔而設計的。透過嵌入額外的文件和數據，它可以確保所有必要的元件都包含在 PDF 文件本身中，從而降低隨著時間的推移資訊遺失或外部依賴性的風險。此功能使其適合以保證長期可訪問性和一致性的方式歸檔文件。