---
title: 在 PDF 文件中新增重複列
linktitle: 在 PDF 文件中新增重複列
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中新增重複列。
type: docs
weight: 20
url: /zh-hant/net/programming-with-tables/add-repeating-column/
---
在本教學中，我們將學習如何使用 Aspose.PDF for .NET 在 PDF 文件中新增重複列。我們將一步步解釋C#的原始碼。在本教學結束時，您將了解如何在 PDF 文件中建立帶有重複列的表格。讓我們開始吧！

## 第一步：建構環境
首先，請確保您已使用 Aspose.PDF for .NET 設定 C# 開發環境。新增對庫的引用並導入必要的命名空間。

## 第 2 步：建立 PDF 文檔
在此步驟中，我們建立一個新的 PDF 文件。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

我們創建了一個空的 PDF 文檔，可以在其中添加內容。

## 第 3 步：建立表
在此步驟中，我們建立一個主表（`outerTable`）和巢狀表（`mytable`）這將在該列中重複。

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

我們指定了表屬性，例如列寬和巢狀表分隔模式。

## 步驟 4：將表格新增至文件中
現在我們將建立的表格新增到 PDF 文件中。

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

我們先加入主表（`outerTable`) 到 PDF 文件。接下來，我們新增巢狀表（`mytable` ) 作為主表單元格中的一個段落。我們也指定重複列的數量`mytable`（在本例中為 5 列）。

## 第 5 步：新增標題和行
現在我們將標題和行新增到表中。

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ……
//在這裡添加其他標題

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ……
     //在此處新增其他列
}
```

我們首先將標題新增到表格的第一行（`headerRow`）。然後我們添加循環中的資料行。在此範例中，我們新增 6 行資料。

## 第6步：儲存PDF文檔
最後，我們將PDF文檔儲存到指定的文件中。

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

確保指定正確的目錄和檔案名稱來儲存輸出 PDF 檔案。

### 使用 Aspose.PDF for .NET 新增重複列的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
//建立一個新文檔
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

//實例化一個佔據整個頁面的外表
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//實例化一個表格對象，該對象將嵌套在outerTable中，該對象將在同一頁面內中斷
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

//將outerTable加入到頁面段落中
//將 mytable 加入outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

//新增標題行
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	//在表格中建立行，然後在行中建立儲存格
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 文件中新增重複列。您可以使用此逐步指南在您自己的 C# 專案中建立具有重複列的表。

### 在 PDF 文件中新增重複列的常見問題解答

#### Q：我可以自訂嵌套表中重複列的數量嗎？

答：是的，您可以自訂嵌套表中重複列的數量。在提供的範例中，我們設定`mytable.RepeatingColumnsCount = 5;`，這意味著將有 5 個重複列。您可以將此值變更為任何所需的數字。

#### Q：是否可以動態為巢狀表新增更多行？

答：是的，您可以按照教程中所示的相同方式為巢狀表動態新增更多行。您可以使用循環或任何其他邏輯根據您的資料添加行。

#### Q：我可以將樣式和格式套用到表格及其儲存格嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將樣式和格式套用至表格及其儲存格。該庫提供了各種屬性和方法來自訂表及其內容的外觀。

#### Q：Aspose.PDF for .NET 與 .NET Core 相容嗎？

答：是的，Aspose.PDF for .NET 與 .NET Core 相容。您可以在 .NET Framework 和 .NET Core 應用程式中使用它。

#### Q：我可以使用此方法在現有 PDF 文件中新增重複列嗎？

答：是的，您可以使用此方法在現有 PDF 文件中新增重複列。只需使用 Aspose.PDF for .NET 載入現有文檔，然後按照相同的步驟建立和新增重複列。