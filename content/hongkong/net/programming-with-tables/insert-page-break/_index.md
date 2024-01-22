---
title: 在 PDF 檔案中插入分頁符
linktitle: 在 PDF 檔案中插入分頁符
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中插入分頁符號。
type: docs
weight: 110
url: /zh-hant/net/programming-with-tables/insert-page-break/
---
在本教學中，我們將學習如何使用 Aspose.PDF for .NET 在 PDF 檔案中插入分頁符號。我們將一步步解釋C#的原始碼。在本教學結束時，您將了解如何在 PDF 文件表格中的一定行數之後新增分頁符號。開始吧！

## 第一步：建構環境
請確定您已使用 Aspose.PDF for .NET 配置 C# 開發環境。新增對庫的引用並導入必要的命名空間。

## 步驟2：建立文件和表格
我們建立一個新的 Document 實例並為該文件新增一個頁面。接下來，我們建立一個 Table 實例來表示 PDF 文件中的表格。我們也定義了表格的邊框樣式。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## 步驟 3：在表格中新增一行
我們使用循環向數組添加 200 行。對於每一行，我們建立一個 Row 實例並新增兩個包含文字內容的儲存格。

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     //當新增 10 行時，我們插入一個新的分頁符
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## 步驟 4：將表格新增至文件中
我們將表格新增到文件頁面的段落集合中。

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## 第 5 步：儲存文檔
我們儲存插入分頁符號的 PDF 文件。

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### 使用 Aspose.PDF for .NET 插入分頁符號的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//實例化文件實例
Document doc = new Document();
//將頁面新增至 PDF 檔案的頁面集合
doc.Pages.Add();
//建立表格實例
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
//設定表格邊框樣式
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//設定表格的預設邊框樣式，邊框顏色為紅色
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//指定表列寬度
tab.ColumnWidths = "100 100";
//建立一個循環為表格新增 200 行
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	//新增 10 行時，在新頁面中呈現新行
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
//將表格新增至 PDF 檔案的段落集合中
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 文件中插入分頁符號。您可以使用此逐步指南，使用 C# 在 PDF 文件的表格中的特定行數之後新增分頁符號。

### 在 PDF 檔案中插入分頁符號的常見問題解答

#### Q：如何更改分頁後建立的新頁面的頁面大小？

答：要變更分頁符號後建立的新頁面的頁面大小，您可以設定`PageSize`的財產`Page`目的。例如，您可以使用以下程式碼將頁面尺寸設定為A4：

```csharp
//將頁面大小設定為A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Q：我可以控制分頁後新頁面的頁邊距嗎？

答：是的，您可以控制分頁後新頁面的頁邊距。使用`Margin`的財產`Page`物件設定頁邊距。例如，要將所有邊距設定為 10 磅，可以使用以下代碼：

```csharp
//將所有邊距設定為 10 點
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Q：分頁後的新頁面是否可以新增頁首和頁尾？

答：是的，您可以在分頁符號後的新頁面中新增頁首和頁尾。使用`Page.Header`和`Page.Footer`屬性將內容新增至頁面的頁首和頁尾部分。例如：

```csharp
//將標題新增至新頁面
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

//將頁尾新增至新頁面
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Q：除了一定數量的行之後，我可以在特定位置插入分頁符號嗎？

答：是的，您可以在特定位置插入分頁符，而不是在一定行數之後。您可以設定`IsInNewPage`行的屬性為`true`強製表在該行之後開始一個新頁面。

#### Q：如何依內容高度調整分頁行為？

答：您可以使用`IsBroken`表的屬性可啟用或停用跨頁自動斷行。當設定為`true`，它允許根據內容高度跨頁面分隔行。