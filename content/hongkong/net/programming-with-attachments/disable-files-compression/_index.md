---
title: 禁用 PDF 檔案中的檔案壓縮
linktitle: 禁用 PDF 檔案中的檔案壓縮
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 停用 PDF 檔案中的檔案壓縮。逐步指南，方便操作。
type: docs
weight: 30
url: /zh-hant/net/programming-with-attachments/disable-files-compression/
---
在本教學中，我們將引導您逐步完成以下 C# 原始碼，以使用 Aspose.PDF for .NET 停用 PDF 中的檔案壓縮。

在開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也具備 C# 程式設計的基礎知識。

### 第 1 步：文檔目錄設置

在提供的原始程式碼中，您需要指定要停用檔案壓縮的 PDF 檔案所在的目錄。將“dataDir”變數變更為所需的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 步驟 2：開啟現有 PDF 文檔

我們使用指定的路徑開啟現有的 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 步驟 3：設定新文件以新增為附件

我們配置要新增為附件的新檔案。在此範例中，我們新增一個名為「test_out.txt」和描述「範例文字檔案」的文字檔案。

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### 步驟 4：停用檔案壓縮

我們透過將 FileSpecification 物件的 Encoding 屬性設為 FileEncoding.None 來停用檔案壓縮。

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### 步驟 5：將附件新增至文件的附件集合中

我們將附件新增到文件的附件集合中。

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### 第 6 步：儲存新的輸出文件

最後，我們將產生的新 PDF 檔案以名稱「DisableFilesCompression_out.pdf」保存在指定目錄中。

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### 使用 Aspose.PDF for .NET 停用檔案壓縮的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
//設定要新增為附件的新文件
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
//指定 Encoding proparty 將其設定為 FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
//將附件新增至文件的附件集合
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
//儲存新輸出
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 停用 PDF 中的檔案壓縮。現在您可以使用這些知識來維護附加檔案的完整性，而無需壓縮。

## 在 PDF 文件中禁用文件壓縮的常見問題解答

#### Q：為什麼我要在 PDF 文件中停用文件壓縮？

答：停用文件壓縮可確保 PDF 文件中的附加文件保持未壓縮狀態，從而保留其原始品質和內容。

#### Q：停用文件壓縮對 PDF 附件有何好處？

答：停用壓縮可以防止壓縮過程中可能發生的任何資料或品質損失，從而確保附加文件按原樣呈現。

#### Q：我可以使用本教學選擇性地停用特定附件的壓縮嗎？

答：是的，本教學將引導您停用 PDF 文件中各個附件的文件壓縮，從而提供細粒度的控制。

#### Q：我可以對哪些類型的附件停用壓縮？

答：您可以對任何類型的附件（例如映像、文件、電子表格等）停用壓縮，以確保保持其完整性。

#### Q：停用壓縮會影響 PDF 文件的整體檔案大小嗎？

答：停用附件壓縮可能會導致 PDF 文件的整體文件大小略有增加，因為未壓縮的文件會佔用更多空間。

#### Q：Aspose.PDF for .NET 如何促進停用檔案壓縮的過程？

答：Aspose.PDF for .NET 提供了一個易於使用的 API，可讓您停用附件的檔案壓縮，如提供的原始程式碼所示。

#### Q：如果需要，我可以稍後重新啟用附件壓縮嗎？

答：是的，如有必要，您可以修改附件的設定以再次啟用壓縮。

#### Q：如果我在支援壓縮的裝置或軟體上開啟 PDF，會發生什麼事？

答：如果您在支援壓縮的裝置或軟體上開啟 PDF，附件可能會以未壓縮的形式顯示，這可能會影響檔案大小和渲染效能。

#### Q：是否存在建議禁用壓縮的特定場景？

答：對於優先考慮保持原始品質和資料完整性的附件（例如高解析度影像或敏感文件），建議停用壓縮。