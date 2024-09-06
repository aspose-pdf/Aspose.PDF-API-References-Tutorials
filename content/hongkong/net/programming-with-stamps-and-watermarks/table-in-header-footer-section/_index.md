---
title: 頁首頁尾部分中的表格
linktitle: 頁首頁尾部分中的表格
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首/頁尾部分新增表格。
type: docs
weight: 170
url: /zh-hant/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首或頁尾部分新增表格。提供的 C# 原始程式碼向您展示如何建立空白 PDF 文件、新增頁面、配置標題部分、建立表格、向表格新增行和儲存格，最後儲存 PDF 文件。

## 第一步：建構環境

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 第 2 步：建立 PDF 文件和頁面

第一步是建立一個實例`Document`類別並為文檔添加頁面。方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//實例化一個文檔對象
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//在 PDF 文件中建立頁面
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

請務必將「您的文件目錄」替換為您要儲存 PDF 文件的目錄的實際路徑。

## 步驟 3：配置標頭部分

現在我們將透過建立一個實例來配置 PDF 文件的標題部分`HeaderFooter`班級。方法如下：

```csharp
//為 PDF 檔案建立標題部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//定義頁面的標題部分
page. Header = header;

//設定標題部分的上邊距
header. Margin. Top = 20;
```

## 第四步：建立表

現在我們將使用以下命令建立一個表`Table`類別並將其新增至標題部分的段落集合中。方法如下：

```csharp
//實例化一個Table對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//將表格新增至標題部分的段落集合中
header.Paragraphs.Add(tab1);

//定義表格列的寬度
tab1.ColumnWidths = "60,300";
```

上面的程式碼建立了一個具有兩列指定寬度的表格。

## 步驟 5：在表格中新增行和儲存格

現在我們將使用以下命令將行和單元格新增至表格中`Row`類和`Cell`班級。方法如下：

```csharp
//在表格中建立一行並新增儲存格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

//合併第一行的第一個儲存格
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//在表格中建立另一行並新增帶有影像的儲存格
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## 第6步：儲存PDF文檔

將表格新增至標題部分後，我們就可以儲存 PDF 文件。方法如下：

```csharp
//儲存 PDF 文件
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

請務必將「您的文件目錄」替換為您要儲存 PDF 文件的目錄的實際路徑。

### 使用 Aspose.PDF for .NET 的頁首頁尾部分中的表格的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//透過呼叫空建構函式實例化 Document 實例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//在 pdf 文件中建立頁面
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//建立 PDF 檔案的標題部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//設定 PDF 檔案的奇數頁眉
page.Header = header;

//設定標題部分的上邊距
header.Margin.Top = 20;

//實例化一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//將表格新增至所需部分的段落集合中
header.Paragraphs.Add(tab1);

//使用 BorderInfo 物件設定預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//設定表格的列寬
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

//將第一行的行跨距值設為 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row2 = tab1.Rows.Add();

//設定 Row2 的背景顏色
row2.BackgroundColor = Color.White;

//新增儲存影像的儲存格
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

//將影像寬度設定為 60
img.FixWidth = 60;

//將圖像新增至表格單元格
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//設定文字的垂直對齊方式為居中對齊
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

//儲存 PDF 文件
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## 結論

恭喜！您已經了解如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首或頁尾部分新增表格。現在，您可以透過新增表格來自訂頁首和頁尾，以在 PDF 文件中顯示其他資訊。

### 頁首頁尾部分錶格的常見問題解答

#### Q：在 PDF 文件的頁首或頁尾部分新增表格的目的是什麼？

答：在 PDF 文件的頁首或頁尾部分新增表格可讓您顯示結構化且有組織的訊息，例如標題、副標題、標誌或您希望在文件每一頁上一致顯示的任何其他內容。

#### Q：提供的C#原始碼如何實作在PDF文件的頁首或頁尾部分新增表格？

答：程式碼示範了建立空白 PDF 文件、新增頁面、設定標題部分、建立包含行和儲存格的表格以及最後儲存 PDF 文件的過程。結果是在 PDF 文件的標題部分顯示一個表格。

#### Q：我可以自訂表格儲存格的外觀，例如邊框、背景顏色和文字樣式嗎？

答：是的，您可以透過設定單元格邊框、背景顏色、文字樣式、字體、字體大小等屬性來自訂表格單元格的外觀。

#### Q：如何將表格新增至 PDF 文件的頁首部分？

A：程式碼將表格新增到頁首部分的段落集合中，這樣可以確保表格顯示在每個頁面的頁首中。

#### Q：我可以根據需要在表格中新增更多行和儲存格嗎？

答：當然，您可以使用以下命令為表格添加更多行和單元格`Rows.Add()`和`Cells.Add()`方法。這允許您根據需要建立表格內容。

#### Q：可以調整表格列的寬度嗎？
答：是的，您可以使用`ColumnWidths`財產。這使您能夠控製表的佈局。

#### Q：如何將儲存格跨越表格中的多列或多行？
答：要將儲存格跨多列，您可以使用`ColSpan`對應單元格的屬性。同樣，您可以使用`RowSpan`屬性將單元格跨多行。

#### Q：如果我想在 PDF 文件的頁首和頁尾部分新增表格，會發生什麼事？

答：您可以對頁首和頁尾部分採用類似的方法。只需創建一個`HeaderFooter`頁腳的實例，配置它，並將表格新增到其段落集合中。

#### Q：我可以在表格單元格內使用圖像嗎？

答：是的，您可以在表格單元格中新增圖像。該程式碼範例演示了透過創建一個`Image`對象，設定其文件路徑和尺寸，然後將其添加到單元格的段落中。

#### Q：如何確保表格在 PDF 文件的所有頁面上一致顯示？

答：當您使用`HeaderFooter`例如，Aspose.PDF 確保表格在每個頁面上顯示一致，提供統一的佈局。