---
title: 將 Excel 工作表資料匯出到表
linktitle: 將 Excel 工作表資料匯出到表
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將資料從 Excel 工作表匯出到 PDF 表。
type: docs
weight: 70
url: /zh-hant/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
在本教程中，我們將學習如何使用 Aspose.PDF for .NET 庫從 Excel 工作表匯出資料並在 PDF 文件中建立表格。我們將逐步瀏覽原始程式碼並詳細解釋每個部分。在本教學結束時，您將能夠產生包含 Excel 工作表資料的表格的 PDF 檔案。讓我們開始吧！

## 要求
在我們開始之前，請確保您具備以下條件：

- C# 程式語言基礎知識
- 您的電腦上安裝了 Visual Studio
- Aspose.PDF for .NET 庫已新增至您的專案中

## 第 1 步：設定環境
首先，在 Visual Studio 中建立一個新的 C# 專案。透過在解決方案資源管理器中右鍵點擊您的項目，選擇“管理 NuGet 套件”並搜尋“Aspose.PDF”，新增對 Aspose.PDF for .NET 程式庫的參考。安裝軟體包即可開始使用。

## 第 2 步：載入 Excel 工作表
在程式碼的第一步中，我們定義包含 Excel 文件的目錄的路徑。將「您的文件目錄」替換為 Excel 檔案所在的實際目錄路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

在這裡，我們使用 Aspose.Cells 庫來載入 Excel 工作簿。確保將“newBook1.xlsx”替換為 Excel 檔案的名稱。

## 第 3 步：訪問工作表
接下來，我們需要存取 Excel 文件中的第一個工作表。我們使用`Worksheets`的集合`Workbook`目的。

```csharp
//存取 Excel 文件中的第一個工作表
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

如果您的 Excel 檔案包含多個工作表，您可以變更索引值`[0]`存取不同的工作表。

## 第四步：匯出資料到DataTable
現在，我們將 Excel 工作表的內容匯出到`DataTable`目的。我們使用以下命令指定要匯出的儲存格範圍`ExportDataTable`方法。

```csharp
//將從第一個單元格開始的7行2列的內容匯出到DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

在此範例中，我們匯出工作表中從第一個儲存格 (0, 0) 到最後一個儲存格的所有行和列。根據您的要求設定合適的範圍。

## 第 5 步：建立 PDF 文檔
現在，我們將使用 Aspose.PDF 庫建立一個新的 PDF 文件。

```csharp
//實例化一個 Document 實例
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

這將創建一個空的 PDF 文檔，我們可以在其中添加內容。

## 步驟 6：新增頁面和表格
為了以表格格式顯示數據，我們需要在PDF文件中新增頁面和表格。

```csharp
//在文件實例中建立頁面
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//建立一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//在節的段落集合中新增 Table 對象
sec1.Paragraphs.Add(tab1);
```

在這裡，我們建立一個新頁面和一個表格物件。然後，我們將該表新增到頁面的段落集合中。

## 第7步：設定表屬性
在匯入資料之前，我們需要設定表格的一些屬性，例如列寬和預設儲存格邊框。

```csharp
//設定表格的列寬
tab1.ColumnWidths = "40 100 100";

//使用 BorderInfo 物件設定表格的預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

在此範例中，我們將列寬設定為 40、100 和 100 個單位。根據您的資料調整值。我們還設定預設儲存格邊框以在每個儲存格的所有側面顯示邊框。

## 步驟8：將資料匯入表中
現在，我們將從以下位置導入數據`DataTable`使用以下方法將物件放入表中`ImportDataTable`方法。

```csharp
//將資料從上面建立的 DataTable 匯入到 Table 物件中
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

在這裡，我們指定要匯入的行和列的範圍。在此範例中，我們從以下位置匯入所有行和列`dataTable`目的。

## 步驟 9：格式化表格
為了增強表格的外觀，我們可以將格式套用到特定的儲存格或行。在此步驟中，我們將格式化表格的第一行和備用行。

```csharp
//取得表中的第一行
Aspose.Pdf.Row row1 = tab1.Rows[0];

//設定第一行的格式
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     //設定第一行單元格的背景顏色
     curCell.BackgroundColor = Color.Blue;//設定第一行單元格的面
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     //設定第一行單元格的字體顏色
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     //設定第一行單元格的文字對齊方式
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

//交替行格式
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         //設定交替行中儲存格的背景顏色
         curCell.BackgroundColor = Color.Gray;
        
         //設定交替行中儲存格的文字顏色
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

在這裡，我們迭代第一行中的儲存格並設定它們的背景顏色、字體、字體顏色和文字對齊方式。然後，我們迭代交替行中的所有單元格並設定它們的背景和文字顏色。

## 第10步：儲存PDF文檔
最後，我們將PDF文檔儲存到指定位置。

```csharp
//儲存 PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

確保將“您的文件目錄”替換為輸出 PDF 檔案所需的目錄路徑和檔案名稱。

### 使用 Aspose.PDF for .NET 將 Excel 工作表資料匯出到表格的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
//存取 Excel 文件中的第一個工作表
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
//將從第一個單元格開始的7行2列的內容匯出到DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

//實例化文件實例
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
//在文件實例中建立頁面
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//建立一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//在節的段落集合中新增 Table 對象
sec1.Paragraphs.Add(tab1);

//設定表格的列寬。我們需要手動指定 ColumnCount。
//由於目前 Excel 工作表具有三列，因此我們指定相同的計數
tab1.ColumnWidths = "40 100 100";

//使用 BorderInfo 物件設定表格的預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//將資料從上面建立的 DataTable 匯入到 Table 物件中
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
//取得表中的第一行
Aspose.Pdf.Row row1 = tab1.Rows[0];

//遍歷第一行中的所有單元格並將其背景顏色設為藍色
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	//設定表格第一行中所有儲存格的背景。
	curCell.BackgroundColor = Color.Blue;
	//設定表中第一行單元格的字體。
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//設定表格第一行中所有儲存格的字體顏色。
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	//將第一行單元格的文字對齊方式設定為居中。
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	//遍歷第一行中的所有單元格並將其背景顏色設為藍色
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		//設定除第一行之外的所有單元格的背景顏色。
		curCell.BackgroundColor = Color.Gray;
		//設定除第一行之外的所有單元格的文字顏色。
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

//儲存 PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 函式庫將資料從 Excel 工作表匯出到 PDF 表格。我們介紹了載入 Excel 工作表、建立 PDF 文件、新增表格、匯入資料以及設定表格格式的逐步流程。現在您可以透過程式設計產生包含 Excel 資料的表格的 PDF 檔案。

### 常見問題解答

#### Q：將 Excel 工作表資料匯出到 PDF 表格的目的為何？

答：將 Excel 工作表資料匯出到 PDF 表格可以讓您以結構化且有組織的格式呈現資料。它使您能夠生成帶有包含 Excel 工作表資料的表格的 PDF 文件，從而更輕鬆地以便攜式文件格式共享和保存資訊。

#### Q：我可以自訂 PDF 表格的外觀嗎？

答：是的，您可以使用 Aspose.PDF for .NET 提供的各種屬性來自訂 PDF 表格的外觀。在提供的 C# 原始程式碼中，您可以修改列寬、儲存格邊框、文字對齊方式、字體樣式等，以滿足您的特定要求。

#### Q：如何處理包含多個工作表的 Excel 檔案？

答：在提供的 C# 程式碼中，我們使用索引存取了 Excel 檔案中的第一個工作表`[0]`。如果您的Excel檔案包含多個工作表，您可以透過相應地變更索引值來存取它們，例如`[1]`對於第二個工作表或`[2]`對於第三個工作表。

#### Q：我可以對 PDF 表格中的特定行或儲存格套用不同的格式嗎？

答：是的，您可以對 PDF 表格中的特定行或儲存格套用不同的格式。在提供的 C# 原始程式碼中，我們示範如何透過更改背景顏色、字體樣式和字體顏色來以不同方式設定第一行和備用行的格式。您可以根據需要將類似的格式化技術套用至任何特定行或儲存格。

#### Q：Aspose.PDF for .NET 是唯一允許將 Excel 資料匯出到 PDF 表格的資料庫嗎？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，用於在 .NET 應用程式中處理 PDF 文件。雖然可能還有其他庫可用，但 Aspose.PDF for .NET 提供了廣泛的特性和功能，用於從 Excel 資料生成、操作和匯出帶有表格的 PDF 文件，使其成為此類任務的熱門選擇。