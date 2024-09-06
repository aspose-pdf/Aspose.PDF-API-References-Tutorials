---
title: PDF 檔案中表格內的 HTML 標籤
linktitle: PDF 檔案中表格內的 HTML 標籤
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案的表格內使用 HTML 標籤。
type: docs
weight: 100
url: /zh-hant/net/programming-with-tables/html-tags-inside-table/
---
在本教學中，我們將學習如何使用 Aspose.PDF for .NET 在 PDF 文件的表格內使用 HTML 標籤。我們將一步步解釋C#的原始碼。在本教學結束時，您將了解如何將 HTML 內容插入 PDF 文件的表格中。讓我們開始吧！

## 第一步：建構環境
請確定您已使用 Aspose.PDF for .NET 配置 C# 開發環境。新增對庫的引用並導入必要的命名空間。

## 步驟2：建立表格數據
我們建立一個包含字串類型的「資料」列的資料表。然後，我們使用 HTML 內容將行新增至此 DataTable。

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## 第 3 步：建立文件和表格
我們建立一個新的 PDF 文件並在該文件中新增一個頁面。接下來，我們初始化 Table 類別的實例並設定表屬性。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## 第四步：將資料匯入表中
我們使用“ImportDataTable”方法將資料從 DataTable 匯入到表中。我們指定方法參數來指示應匯入 DataTable 的行和列的範圍。

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## 步驟 5：將表格新增至文件中
我們將表格新增到文件頁面。

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## 第 6 階段：儲存文檔
我們將 PDF 文件與包含 HTML 內容的表格一起儲存。

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### 使用 Aspose.PDF for .NET 的 HTML Tags Inside Table 的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
//初始化表的新實例
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//設定表格的列寬
tableProvider.ColumnWidths = "400 50 ";
//將表格邊框顏色設定為淺灰色
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//設定表格單元格的邊框
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 文件的表格內使用 HTML 標籤。您可以使用此逐步指南，使用 C# 將 HTML 內容插入 PDF 文件的表格儲存格中。

### PDF 檔案中表格內 HTML 標籤的常見問題解答

#### Q：我可以在表格單元格內使用其他 HTML 標籤和屬性嗎？

答：是的，您可以在表格單元格內使用各種 HTML 標籤和屬性，例如`<b>`, `<i>`, `<a>`，等等。 Aspose.PDF for .NET 支援多種 HTML 元素和樣式，您可以使用它們來格式化表格單元格中的內容。

#### Q：我可以將 CSS 樣式套用到表格儲存格內的 HTML 內容嗎？

答：是的，您可以將 CSS 樣式套用到表格儲存格內的 HTML 內容。 Aspose.PDF for .NET 提供可套用於 HTML 元素的基本 CSS 樣式的支援。

#### Q：是否可以在表格單元格內新增圖像和 HTML 內容？

答：是的，您可以在表格單元格內新增圖像和 HTML 內容。您可以使用 HTML`<img>`標籤以包含來自各種來源的圖像，例如本機檔案或 URL。

#### Q：如何為表格指定不同的列寬？

答：您可以使用以下命令為表格指定不同的列寬`ColumnWidths`表的屬性。此屬性採用包含空格分隔值的字串，其中每個值代表列的寬度（以磅為單位）。

#### Q：我可以在包含 HTML 內容的儲存格內使用巢狀表格嗎？

答：是的，您可以在包含 HTML 內容的儲存格內使用巢狀表格。您可以建立單獨的表格實例並將它們新增為單元格內 HTML 內容的一部分以實現嵌套效果。