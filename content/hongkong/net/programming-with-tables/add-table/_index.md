---
title: 在 PDF 檔案中新增表格
linktitle: 在 PDF 檔案中新增表格
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆新增表單。
type: docs
weight: 40
url: /zh-hant/net/programming-with-tables/add-table/
---
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立、操作和轉換 PDF 文件。在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 在 PDF 檔案中新增表格的過程。我們將解釋所提供的程式碼片段的每個步驟，並提供全面的指南來幫助您理解和在自己的專案中實現該功能。

## 介紹

PDF 文件廣泛用於以便攜式格式共用和保存資訊。在 PDF 文件中新增表格可以增強其視覺外觀，並使資料呈現更加有條理和結構化。 Aspose.PDF for .NET 提供了一種向現有 PDF 文件新增表格或從頭開始建立新文件的便利方法。

## 什麼是 Aspose.PDF for .NET？

Aspose.PDF for .NET 是一個功能強大且功能豐富的程式庫，可讓 .NET 開發人員以程式設計方式建立、操作和轉換 PDF 文件。它提供了廣泛的功能，包括從頭開始建立 PDF 文件、修改現有 PDF 文件、合併或分割 PDF 文件、添加文字、圖像和表格、從 PDF 中提取資料等等。透過 Aspose.PDF for .NET，開發人員可以自動執行複雜的 PDF 相關任務並提供高品質的 PDF 解決方案。

## 將表格新增至 PDF 文件

若要使用 Aspose.PDF for .NET 將表格新增至 PDF 文檔，請按照以下逐步指南進行操作：

## 第 1 步：載入來源 PDF 文檔

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

上面的程式碼片段載入您想要新增表格的來源 PDF 文件。確保提供 PDF 檔案的正確路徑。

## 步驟 2：初始化表格的新實例

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

在此步驟中，我們建立 Table 類別的一個新實例，它表示 PDF 文件中的表格。

## 第三步：設定表格邊框顏色

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

在這裡，我們使用 BorderInfo 類別來設定表格的邊框顏色。您可以根據您的要求自訂邊框樣式、寬度和顏色。

## 步驟 4：設定表格儲存格的邊框

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

我們也使用表格物件的 DefaultCellBorder 屬性來設定表格單元格的邊框。這可確保表中的每個儲存格都有指定的邊框樣式、寬度和顏色。

## 步驟 5：在表格中新增行和儲存格

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

在此步驟中，我們建立一個循環以向表中新增 10 行。在每一行中，我們新增三個包含範例資料的儲存格。您可以根據您的特定要求修改程式碼以新增行和儲存格。

## 步驟 6：將表格物件新增至文件中

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
//儲存包含表格物件的更新文檔
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

最後，我們使用對應頁面的 Paragraphs 集合將表格物件新增至 PDF 文件的第一頁。

### 使用 Aspose.PDF for .NET 新增表格的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入來源 PDF 文件
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
//初始化表的新實例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//將表格邊框顏色設定為淺灰色
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//設定表格單元格的邊框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//建立一個循環以添加 10 行
for (int row_count = 1; row_count < 10; row_count++)
{
	//將行加入表中
	Aspose.Pdf.Row row = table.Rows.Add();
	//新增表格單元格
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
//將表格物件新增至輸入文件的第一頁
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
//儲存包含表格物件的更新文檔
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## 結論

在本教學中，我們解釋了使用 Aspose.PDF for .NET 將表格新增至 PDF 文件的逐步流程。我們介紹了載入來源 PDF 文件、初始化 Table 類別的新實例、設定表格邊框顏色和單元格邊框、向表格新增行和儲存格以及向文件新增表格物件。透過遵循本指南，您可以輕鬆地以程式設計方式將表格合併到 PDF 文件中，並根據您的特定需求進行自訂。

### 在 PDF 文件中新增表格的常見問題解答

#### Q：我可以在表格中新增更多欄位嗎？

答：是的，您可以透過增加新增到每行的儲存格數量來為表格新增更多欄位。在提供的範例中，每行具有代表三列的三個單元格。您可以為每行新增更多儲存格以新增其他列。

#### Q：如何更改表格的外觀，例如字體大小和樣式？

答：您可以透過設定屬性來自訂表格的外觀，包括字體大小和樣式。`Aspose.Pdf.Table`和`Aspose.Pdf.TextFragment`對象。例如，您可以設定`DefaultCellTextState`屬性來更改表格單元格中文字的字體屬性。

#### Q：表格中的儲存格可以合併嗎？

答：是的，您可以使用以下命令合併表格中的儲存格：`MergeCells`的方法`Aspose.Pdf.Row`班級。這允許您建立跨多行和多列的儲存格。

#### Q：我可以為表格單元格新增圖像或其他內容嗎？

答：是的，您可以在表格儲存格中新增各種類型的內容，包括圖像、文字、超連結等。您可以使用 Aspose.PDF for .NET 中的適當類別為儲存格新增不同類型的內容。

#### Q：Aspose.PDF for .NET 與 .NET 5.0 或更高版本相容嗎？

答：是的，Aspose.PDF for .NET 與 .NET 5.0 及更高版本相容。它支援各種.NET平台，包括.NET Framework、.NET Core和.NET 5.0+。