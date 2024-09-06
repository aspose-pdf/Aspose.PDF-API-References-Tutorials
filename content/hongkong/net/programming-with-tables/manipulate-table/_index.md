---
title: 操作 PDF 檔案中的表格
linktitle: 操作 PDF 檔案中的表格
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆操作 PDF 檔案中的表單。
type: docs
weight: 130
url: /zh-hant/net/programming-with-tables/manipulate-table/
---
在本教學中，我們將引導您逐步完成使用 Aspose.PDF for .NET 操作 PDF 檔案中的表格的過程。表格是 PDF 文件中的常見元素，能夠以程式設計方式修改其內容在各種情況下都非常有益。我們將使用提供的 C# 原始程式碼來演示該過程。

## 要求

在我們開始之前，請確保您具備以下條件：

- 安裝了 Visual Studio 或任何其他 C# 開發環境。
- 新增 Aspose.PDF for .NET 函式庫作為專案的參考。

現在，讓我們深入了解使用 Aspose.PDF for .NET 操作 PDF 文件中的表格所需的步驟。

## 第 1 步：載入 PDF 文檔

第一步是將現有的 PDF 文件載入到您的 C# 應用程式中。您需要提供文件所在目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

將「您的文件目錄」替換為 PDF 文件所在目錄的實際路徑。

## 第 2 步：在文件中尋找表格

要操作表格，我們需要在 PDF 文件中找到它們。 Aspose.PDF for .NET提供了一個TableAbsorber類，讓我們可以從文件中提取表格。我們將建立 TableAbsorber 類別的實例並存取文件的所需頁面。

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

在此範例中，我們正在存取文件的第一頁。您可以根據您的要求變更頁碼。

## 第 3 步：存取表格單元格和文字片段

一旦我們有了表格，我們就可以存取它們的單元格和文字片段進行操作。在提供的原始程式碼中，我們正在存取第一個表格、其第一行的第一個儲存格以及該儲存格內的第二個文字片段。

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

您可以根據您的特定需求修改程式碼以針對不同的表格、儲存格或文字片段。

## 第 4 步：操作表格文本

訪問文字片段後，我們現在可以修改其內容。在給定的範例中，我們將文字變更為“hi world”。

```csharp
fragment.Text = "hi world";
```

請隨意將“hi world”替換為您想要的文字。

## 第五步：儲存修改後的文檔

完成所需的修改後，我們需要儲存修改後的 PDF 文件。

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

確保提供已修改文件的路徑和檔案名稱。


### 使用 Aspose.PDF for .NET 操作表的範例原始程式碼

```csharp
try
{
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//載入現有 PDF 文件
	Document pdfDocument = new Document(dataDir + "input.pdf");
	//建立TableAbsorber物件來尋找表
	TableAbsorber absorber = new TableAbsorber();

	//訪問帶有吸收器的第一頁
	absorber.Visit(pdfDocument.Pages[1]);

	//造訪頁面上的第一個表格、第一個儲存格和其中的文字片段
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	//更改單元格中第一個文本片段的文本
	fragment.Text = "hi world";
	dataDir = dataDir + "ManipulateTable_out.pdf";
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nTable manipulated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 操作 PDF 文件中的表格。透過遵循逐步指南，您可以輕鬆載入 PDF 文件、尋找表格、存取儲存格和文字片段、修改表格內容以及儲存修改後的文件。這種方法在處理 PDF 文件中的表格操作時提供了靈活性和效率。

### PDF 檔案中的操作表常見問題解答

#### Q：我可以操作多頁 PDF 文件中的表格嗎？

答：是的，您可以使用 Aspose.PDF for .NET 操作多頁 PDF 文件中的表格。在提供的範例中，我們訪問了文件的第一頁（`pdfDocument.Pages[1]`），但您可以循環遍歷所有頁面並根據需要操作每個頁面上的表格。

#### Q：如何為現有資料表新增行或新列？

答：若要新增行或新列，您可以使用 Aspose.PDF for .NET 提供的 API。您可以訪問`RowList`和`CellList`的屬性`TableAbsorber.TableList`以程式設計方式新增行和儲存格。如需詳細資訊和程式碼範例，請參閱 Aspose.PDF for .NET 文件。

#### Q：是否可以從 PDF 文件中刪除表格？

答：是的，您可以使用 Aspose.PDF for .NET 從 PDF 文件中刪除表格。為此，您可以刪除特定的`Table`對象從`Page.Paragraphs`收藏。您可以使用下列屬性來標識要刪除的表`Table.NumberOfColumns`, `Table.NumberOfRows`，以及其他唯一識別碼。

#### Q：我可以更改表格文字的格式（字體、顏色、對齊方式）嗎？

答：是的，您可以使用 Aspose.PDF for .NET 來變更表格文字的格式。您可以訪問`TextState`的財產`TextFragment`物件修改文字的字體、字體大小、顏色和對齊方式。

#### Q：Aspose.PDF for .NET 支援使用 PDF 表單 (AcroForms) 中的表格嗎？

答：是的，Aspose.PDF for .NET 支援使用 PDF 表單 (AcroForms) 中的表格。您可以存取和操作 PDF 表單中的表格元素，類似於本教學中示範的方法。 Aspose.PDF for .NET 為使用 AcroForms 和表單欄位提供了廣泛的支援。