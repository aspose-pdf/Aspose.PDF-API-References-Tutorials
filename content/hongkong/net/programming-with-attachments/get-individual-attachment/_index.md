---
title: 取得 PDF 文件中的單獨附件
linktitle: 取得 PDF 文件中的單獨附件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 取得 PDF 檔案中的單一附件。
type: docs
weight: 60
url: /zh-hant/net/programming-with-attachments/get-individual-attachment/
---
在本教學中，我們將引導您逐步完成以下 C# 原始程式碼，以使用 Aspose.PDF for .NET 取得 PDF 檔案的單獨附件。

在開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也具備 C# 程式設計的基礎知識。

### 第 1 步：文檔目錄設置

在提供的原始程式碼中，您需要指定要從中取得單一附件的 PDF 檔案所在的目錄。將“dataDir”變數變更為所需的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 步驟 2：開啟現有 PDF 文檔

我們使用指定的路徑開啟現有的 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### 第 3 步：取得特定附件

我們從文件的附件集合中檢索特定的附件。在此範例中，我們使用索引 1 來取得第一個附件。

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### 第 4 步：取得檔案屬性

我們顯示附件屬性，例如名稱、描述、MIME 類型、控制雜湊、建立日期、修改日期和大小。

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

//檢查物件參數是否包含附加資訊
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### 步驟 5：檢索附件並儲存到文件

我們檢索附件的內容並將其儲存到文字檔案中。在此範例中，檔案以名稱“test_out.txt”儲存。

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### 使用 Aspose.PDF for .NET 取得個人附件的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
//取得特定的嵌入文件
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
//取得檔案屬性
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
//檢查參數物件是否包含參數
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
//取得附件並寫入檔案或串流
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 從 PDF 檔案取得單一附件。現在您可以使用這些知識從 PDF 文件中提取並保存附件。

### 在 PDF 文件中獲取單一附件的常見問題解答

#### Q：從 PDF 文件中取得單一附件的目的是什麼？

答：取得單獨的附件可讓您提取並保存 PDF 中的特定嵌入文件，這對於進一步分析或操作非常有用。

#### Q：我如何在 PDF 相關任務中從本教學中受益？

答：本教學提供逐步說明和 C# 原始程式碼，用於使用 Aspose.PDF for .NET 從 PDF 文件擷取和儲存特定附件。

#### Q：使用本教學我可以存取哪些附件屬性？

答：您可以存取附件屬性，例如特定附件的名稱、描述、MIME 類型、控制雜湊、建立日期、修改日期和大小。

#### Q：我可以修改程式碼來取得第一個附件以外的附件嗎？

答：當然可以，您可以調整索引（例如，`pdfDocument.EmbeddedFiles[1]`) 以檢索 PDF 中不同索引處的附件。

#### Q：如何將檢索到的附件儲存到文件中？

答：本教學提供了用於檢索附件內容並將其儲存到具有指定名稱的文字檔案的程式碼。

#### Q：附件資訊中的「Check Hash」屬性有何意義？

答：「Check Hash」屬性代表附件的控制雜湊值，可用於驗證附件的完整性。

#### Q：我可以擴展此知識以提取具有特定條件（例如文件類型）的附件嗎？

答：是的，您可以增強程式碼以根據特定條件（例如文件類型或其他屬性）過濾附件。

#### Q：Aspose.PDF for .NET 如何簡化擷取單一附件的過程？

答：Aspose.PDF for .NET 提供了一個使用者友善的 API，有助於提取和操作 PDF 文件中的附件。

#### Q：本教學也適用於受密碼保護的 PDF 檔案嗎？

答：是的，您可以採用類似的技術，使用 Aspose.PDF for .NET 從受密碼保護的 PDF 檔案中檢索單一附件。
