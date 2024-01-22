---
title: 表格行內容的文字對齊
linktitle: 表格行內容的文字對齊
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 對齊 PDF 表格中的行內容。
type: docs
weight: 210
url: /zh-hant/net/programming-with-tables/text-alignment-for-table-row-content/
---
在本教學中，我們將逐步指導您使用 Aspose.PDF for .NET 對齊 PDF 文件表格中的行內容。我們將解釋提供的 C# 原始程式碼並向您展示如何實現它。

## 第 1 步：建立 PDF 文檔
首先，我們將建立 PDF 文件：

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 步驟2：表初始化
接下來，我們將初始化表：

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 第三步：設定表格邊框顏色
我們將配置表格邊框顏色：

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 步驟 4：設定表格單元格邊框
我們將配置表格單元格邊框：

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 第 5 步：循環向表中新增 10 行
現在，我們將使用循環向表中新增 10 行：

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## 步驟 6：配置垂直線對齊
我們將配置表行的垂直對齊方式：

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## 步驟 7：為行單元格新增內容
我們將向行單元格添加內容：

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## 步驟8：將表格新增至文件頁面
現在讓我們將表格新增到文件頁面：

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## 第9步：儲存PDF文檔
最後，我們儲存PDF文檔：

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### 使用 Aspose.PDF for .NET 進行表格行內容文字對齊的範例原始程式碼

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

//建立 PDF 文件
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//初始化表的新實例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//將表格邊框顏色設定為淺灰色
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//設定表格單元格的邊框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//建立一個循環以添加 10 行
for (int row_count = 0; row_count < 10; row_count++)
{
	//將行加入表中
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
//將表格物件新增至輸入文件的第一頁
tocPage.Paragraphs.Add(table);
//儲存包含表格物件的更新文檔
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## 結論
恭喜！現在您已經了解如何使用 Aspose.PDF for .NET 對齊 PDF 文件表格中的行內容。本逐步指南向您展示如何建立文件、初始化表格、配置邊框和對齊方式、新增內容以及儲存 PDF 文件。現在您可以將這些知識應用到您自己的專案中。

### 常見問題解答

#### Q：如何水平對齊表格單元格的內容？

答：您可以透過設定水平對齊表格單元格的內容`HorizontalAlign`細胞的屬性`TextState`目的。例如，要居中對齊文本，請使用`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center`。您也可以將其設定為`HorizontalAlignment.Left`或者`HorizontalAlignment.Right`分別用於左對齊和右對齊。

#### Q：我可以對表格中的各個儲存格套用不同的邊框樣式和顏色嗎？

答：是的，您可以對表格中的各個儲存格套用不同的邊框樣式和顏色。若要自訂特定儲存格的邊框，請設定`cell.Border`屬性為新的`BorderInfo`具有所需設定的對象，例如邊框邊、寬度和顏色。

#### Q：如何調整儲存格內表格內容的垂直對齊方式？

答：您可以透過設定儲存格內的表格內容的垂直對齊方式`VerticalAlignment`行的屬性為`VerticalAlignment.Center`, `VerticalAlignment.Top`， 或者`VerticalAlignment.Bottom`。此屬性控制該行中所有單元格的垂直對齊方式。

#### Q：是否可以動態地在表格中新增更多列或行？

答：是的，您可以使用以下命令動態在表中新增更多列和行`table.Rows.Add()`新增行的方法和`row.Cells.Add()`方法將新單元格新增至行。您可以在循環內或根據您的特定要求執行此操作。

#### Q：如何為特定儲存格或整個表格設定背景顏色？

答：若要為特定儲存格或整個表格設定背景顏色，請使用`BackgroundColor`的財產`Cell`或者`Table`目的。例如，要設定儲存格的背景顏色，請使用`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.