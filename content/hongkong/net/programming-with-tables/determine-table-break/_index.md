---
title: 確定 PDF 檔案中的表格中斷
linktitle: 確定 PDF 檔案中的表格中斷
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 確定 PDF 檔案中的換表符。
type: docs
weight: 60
url: /zh-hant/net/programming-with-tables/determine-table-break/
---
在本教學中，我們將學習如何使用 Aspose.PDF for .NET 確定 PDF 檔案中的換表符。我們將一步步解釋C#的原始碼。在本教學結束時，您將了解如何確定表格是否超出頁邊距。開始吧！

## 第一步：建構環境
首先，請確保您已使用 Aspose.PDF for .NET 設定 C# 開發環境。新增對庫的引用並導入必要的命名空間。

## 第 2 步：建立 PDF 文檔
在這一步驟中，我們創建一個新的`Document`代表 PDF 文檔的對象。

```csharp
pdf-Document = new Document();
```

該文件將用於新增部分和表格。

## 步驟 3：新增部分和表格
現在我們將在 PDF 文件中新增一個部分，並在該部分內建立表格。

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

我們也指定表格的上邊距為 300 點。您可以根據需要調整該值。

## 第 4 步：表格設置
在此步驟中，我們配置表格屬性，例如列寬和邊框。

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

這裡我們定義表格列和單元格邊框的寬度。您可以根據自己的喜好調整這些數值。

## 步驟 5：在表格中新增行和儲存格
現在我們將使用循環在表中建立行和單元格。

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

此處，我們在表中建立 17 行，並在每行中新增三個儲存格。您可以根據需要調整扣環。

## 第 6 步：確定表中斷
現在，我們將透過將頁面高度與表格中物件的總高度進行比較來確定表格是否超出頁邊距。

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

我們計算頁面的高度和物件的總高度，同時考慮邊距。如果差異為 10 或更少，則表格超出頁邊距。

## 步驟7：儲存PDF文檔
最後，我們將結果儲存為 PDF 文件。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

請務必指定正確的文件目錄。產生的 PDF 檔案將與確定的表格分隔符號一起儲存。

### 使用 Aspose.PDF for .NET 確定表格中斷的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化物件 PDF 類
Document pdf = new Document();
//將部分新增至 PDF 文件部分集合
Aspose.Pdf.Page page = pdf.Pages.Add();
//實例化一個表對象
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
//將表格新增至所需部分的段落集合中
page.Paragraphs.Add(table1);
//設定表格的列寬
table1.ColumnWidths = "100 100 100";
//使用 BorderInfo 物件設定預設儲存格邊框
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//使用另一個自訂的 BorderInfo 物件設定表格邊框
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//建立 MarginInfo 物件並設定其左、下、右、上邊距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//將預設儲存格填入設定為 MarginInfo 對象
table1.DefaultCellPadding = margin;
//如果將計數器增加到 17，桌子就會損壞
//因為這個頁面已經無法容納更多內容了
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//在表格中建立行，然後在行中建立儲存格
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
//取得頁面高度資訊
float PageHeight = (float)pdf.PageInfo.Height;
//獲取頁面上下邊距的總高度信息，
//表格頂部邊距和表格高度。
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

//顯示頁面高度、表格高度、表格上邊距和頁面頂部
//和下邊距資訊
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//檢查是否扣除頁面上邊距 + 頁面下邊距之和
// 表格頂部邊距和表格高度與頁面高度及其減去值
//超過 10（平均行可以大於 10）
if ((PageHeight - TotalObjectsHeight) <= 10)
	//如果該值小於 10，則顯示該訊息。
	//這表明不能放置另一行，如果我們添加新的
	//行、表都會斷。這取決於行高值。
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
//儲存pdf文檔
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 確定 PDF 文件中的換表符。您可以使用此逐步指南來檢查表格是否超出您自己的 C# 專案中的頁邊距。

### 確定 PDF 文件中表格中斷的常見問題解答

#### Q：確定 PDF 文件中的換表符的目的是什麼？

答：確定 PDF 文件中的表格分隔符號的目的是檢查表格是否超出頁邊距。這可確保表格的內容在可用頁面空間內正確顯示。透過偵測表格中斷，您可以處理內容溢位並相應地調整表格佈局。

#### Q：如何調整表格的上邊距？

 A：在提供的C#原始碼中，可以透過修改`table1.Margin.Top`財產。根據需要增加或減少該值以設定所需的表格上邊距。

#### Q：我可以自訂表格的外觀，例如儲存格顏色和字體大小嗎？

答：是的，您可以使用 Aspose.PDF for .NET 提供的各種屬性和方法來自訂表格及其單元格的外觀。例如，您可以變更儲存格背景顏色、字體大小、字體系列、文字對齊方式等。有關如何自訂表格外觀的更多信息，請參閱官方文件。

#### Q：如果表格超出頁邊距怎麼辦？

答：如果表格超出頁邊距，可能會導致內容截斷或重疊，從而降低 PDF 文件的可讀性和組織性。透過偵測表格中斷並處理溢出，您可以確保內容在可用頁面區域內保持正確顯示。

#### Q：我可以確定同一 PDF 文件中多個表格的表格分隔符號嗎？

答：是的，您可以確定同一 PDF 文件中多個表格的表格分隔符號。只需對要分析的每個表格重複這些步驟，並根據需要調整表格佈局以防止內容溢出。