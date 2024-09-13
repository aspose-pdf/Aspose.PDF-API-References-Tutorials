---
title: 在 PDF 文件中渲染表格
linktitle: 在 PDF 文件中渲染表格
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中顯示表格。
type: docs
weight: 170
url: /zh-hant/net/programming-with-tables/render-table/
---
在本教學中，我們將逐步指導您使用 Aspose.PDF for .NET 在 PDF 文件中顯示表格。我們將解釋提供的 C# 原始程式碼並向您展示如何實現它。

## 第 1 步：建立文檔
首先，我們將建立一個新的 PDF 文件：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立一個新文檔
Document doc = new Document();
```

## 步驟 2：設定頁邊距和方向
接下來，我們將配置頁邊距並將方向設定為橫向模式：

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## 步驟 3：建立表格和列
現在讓我們建立一個表格並設定列寬：

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## 步驟 4：在表格中新增行和儲存格
接下來，我們將使用循環將行和單元格新增至表中：

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## 第5步：將表格加入到頁面
現在讓我們將表格新增到文件頁面：

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## 步驟 6：在新頁面上顯示表格
接下來，我們將建立一個新表並將“IsInNewPage”屬性設為“true”以在新頁面上顯示該表：

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## 第7步：儲存PDF
最後，我們儲存PDF文檔：

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 的渲染表示範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
//新增頁面。
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
//我想將表 1 保留到下一頁...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## 結論
恭喜！現在您已經了解如何使用 Aspose.PDF for .NET 在 PDF 文件中顯示表格。本逐步指南向您展示如何建立文件、配置頁邊距和方向、新增表格以及在新頁面上顯示表格。現在您可以將這些知識應用到您自己的專案中。

### PDF 文件中渲染表的常見問題解答

#### Q：如何修改表格的外觀，例如更改儲存格顏色或新增邊框？

 A：要修改表格的外觀，可以設定表格的各種屬性`Aspose.Pdf.Table`及其細胞。例如，您可以設定`BackgroundColor`單元格的屬性來變更其背景顏色。您也可以設定`Border`表格或單一儲存格的屬性來新增邊框。此外，您還可以透過修改表格內容來自訂字體、文字顏色和對齊方式。`TextState`的`TextFragment`新增到單元格的物件。

#### Q：我可以在表格中新增頁首或頁尾嗎？

答：是的，您可以透過在表格的開頭或結尾建立附加行並在儲存格中設定適當的內容來為表格新增頁首或頁尾。您可以透過在這些特定行中新增不同的樣式或內容來獨立於表格內容的其餘部分自訂頁首或頁尾。

#### Q：如何控製表格在頁面上的位置？

A：要控製表格在頁面上的位置，您可以調整`MarginInfo`的`PageInfo`目的。這`MarginInfo`允許您設定頁面的左、右、上、下邊距，這會影響表格的可用空間。您也可以使用`PositioningType`的財產`Aspose.Pdf.Table`控制其在頁面內容區域內的水平和垂直對齊。

#### Q：我可以將表格匯出為不同的文件格式，例如 Excel 或 CSV 嗎？

答：Aspose.PDF for .NET 主要是為處理 PDF 文件而設計的。雖然它可以將 PDF 文件匯出為圖像或 XPS，但它不直接支援將表格匯出為 Excel 或 CSV 等格式。要將表格資料匯出為不同的文件格式，您可能需要使用其他庫或方法將 PDF 內容轉換為所需的格式。

#### Q：如何在表格單元格中新增超連結？

答：若要為表格儲存格新增超鏈接，您可以使用`Aspose.Pdf.WebHyperlink`類別來建立超鏈接，然後將其作為錨點添加到`TextFragment`細胞內。這允許您將 URL 或連結目標與單元格內的特定文字或內容相關聯，從而建立可點擊的超連結。