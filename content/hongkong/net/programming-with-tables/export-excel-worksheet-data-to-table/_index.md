---
title: 將 Excel 工作表資料匯出到表
linktitle: 將 Excel 工作表資料匯出到表
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將 Excel 工作表資料匯出到 PDF 表格。包含程式碼範例、先決條件和有用提示的逐步教學。
type: docs
weight: 70
url: /zh-hant/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## 介紹

您是否曾經需要將 Excel 工作表中的資料匯出到 PDF 文件中，並整齊地排列成表格格式？想像一下，Excel 中有大量數據，但需要將其作為具有專業外觀的 PDF 進行共享。聽起來很複雜，對吧？但使用 Aspose.PDF for .NET，您可以輕鬆完成此任務。在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 將 Excel 工作表資料匯出到 PDF 文件內的表格的過程。我們將一步一步地引導您，分解所有內容，這樣即使您是新手，到最後您也會感覺自己像個專業人士。

## 先決條件

在我們深入編碼之前，讓我們先進行一些設定：

1.  Aspose.PDF for .NET Library – 請確定您已安裝了最新版本。你可以[在這裡下載](https://releases.aspose.com/pdf/net/).
2. Aspose.Cells for .NET Library – 您需要它來處理 Excel 操作。從以下位置下載[這裡](https://releases.aspose.com/cells/net/).
3. .NET 開發環境 – 像 Visual Studio 這樣的工具非常適合程式設計。
4. Excel 檔案 – 準備好包含要匯出的資料的 Excel 檔案。

如果您沒有 Aspose.PDF 和 Aspose.Cells 庫，您可以從[免費試用](https://releases.aspose.com/).

## 導入包

首先，請確保您已在專案中安裝了 Aspose.PDF 和 Aspose.Cells 庫。您可以使用 Visual Studio 中的 NuGet 套件管理器來安裝它們。

以下是如何在 C# 程式碼中匯入必要的套件：

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

現在先決條件已設置，讓我們逐步完成將資料從 Excel 工作表匯出到 PDF 文件中的表格的過程。

## 第 1 步：載入 Excel 工作簿

首先，您需要將 Excel 工作簿載入到程式中。在此步驟中，我們將使用 Aspose.Cells 開啟 Excel 檔案。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入 Excel 工作簿
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

說明：在這裡，我們指定 Excel 檔案所在的目錄路徑，並使用以下命令載入工作簿`Aspose.Cells.Workbook`。一定要調整好`"YOUR DOCUMENT DIRECTORY"`指向您的文件位置。

## 第 2 步：存取第一個工作表

載入工作簿後，我們需要存取儲存資料的第一個工作表。

```csharp
//存取 Excel 文件中的第一個工作表
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

說明：此步驟很簡單 - 我們從工作簿中取得第一個工作表，其中包含要匯出的資料。

## 步驟3：匯出資料到DataTable

現在，讓我們將 Excel 工作表中的資料匯出到 DataTable 物件中，該物件將充當將資料傳輸到 PDF 的中介。

```csharp
//將從第一個單元格開始的7行2列的內容匯出到DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

解釋：`ExportDataTable`方法從工作表的第一個單元格開始提取數據，並跨越所有行和列。然後該數據被儲存在`DataTable`以供進一步使用。

## 第 4 步：建立新的 PDF 文檔

接下來，我們需要使用 Aspose.PDF 建立一個新的 PDF 文件。

```csharp
//實例化一個 Document 實例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//在文件實例中建立頁面
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

說明：在這裡，我們初始化一個新的`Aspose.Pdf.Document`並向其添加一個頁面。此頁面稍後將包含我們根據 Excel 資料建立的表格。

## 第 5 步：在 PDF 中建立表格對象

讓我們繼續在 PDF 文件中建立表格。

```csharp
//建立一個表對象
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

//將Table物件加入到頁面的段落集合中
page.Paragraphs.Add(table);
```

說明：我們建立一個`Aspose.Pdf.Table`物件並將其新增至頁面的段落集合中，這可確保表格顯示在頁面上。

## 第 6 步：設定列寬和邊框

PDF 中的表格需要定義列寬。我們還將添加邊框以使表格更具可讀性。

```csharp
//設定表格的列寬
table.ColumnWidths = "40 100 100";

//設定預設單元格邊框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

說明：我們設定三列的寬度，並為所有單元格提供預設邊框，厚度為`0.1F`.

## 步驟7：將資料從DataTable匯入到PDF表中

現在，是時候將資料從 DataTable 匯入到我們的 PDF 表中了。

```csharp
//將資料從 DataTable 匯入到 Table 對象
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

解釋：`ImportDataTable`方法傳輸所有數據`DataTable`到 PDF 表。這將使用 Excel 工作表中的資料填入表格。

## 第 8 步：設定標題行樣式

讓我們透過更改背景顏色、字體和對齊方式來設定表格標題行的樣式。

```csharp
//取得表中的第一行
Aspose.Pdf.Row headerRow = table.Rows[0];

//設定標題行的樣式
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

說明：我們循環遍歷第一行（標題）中的所有單元格，並將其背景顏色設為藍色，文字顏色設為黃色，並將文字對齊到中心。

## 步驟9：設定剩餘行的樣式

為了區分標題和其餘行，我們為其餘行添加不同的樣式。

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

說明：對於標題以外的所有行，我們設定灰色背景和白色文字顏色。

## 第10步：儲存PDF文檔

最後，將 PDF 文件與表格一起儲存。

```csharp
//儲存 PDF
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

說明：我們將PDF儲存到指定目錄。瞧！您的 Excel 資料現在位於格式精美的 PDF 表格中。

## 結論

現在你就擁有了！只需幾個步驟，您就可以使用 Aspose.PDF for .NET 將資料從 Excel 工作表匯出到 PDF 內的表格中。透過分解流程並對其進行設計，您可以自訂輸出並確保您的數據看起來乾淨且專業。因此，下次有人向您提供 Excel 文件並要求您提供 PDF 報告時，您就知道該怎麼做。

## 常見問題解答

### 我可以對表格進行更多客製化嗎？
絕對地！您可以修改顏色、字型、對齊方式，甚至為特定儲存格新增邊框。

### Aspose.PDF for .NET 是免費的嗎？
它提供免費試用，但要擴展使用，您需要許可證。你可以[在這裡買](https://purchase.aspose.com/buy).

### 我可以只匯出特定的行和列嗎？
是的，可以修改裡面的參數`ExportDataTable`導出特定範圍的方法。

### 這適用於大型 Excel 文件嗎？
是的，Aspose.Cells 旨在高效處理大型 Excel 檔案。

### 如何為 PDF 新增更多頁面？
你可以使用`pdfDocument.Pages.Add()`根據需要新增任意數量的頁面。