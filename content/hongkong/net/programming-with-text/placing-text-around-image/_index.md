---
title: 在 PDF 檔案中將文字放置在圖像周圍
linktitle: 在 PDF 檔案中將文字放置在圖像周圍
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中的影像周圍放置文字。
type: docs
weight: 260
url: /zh-hant/net/programming-with-text/placing-text-around-image/
---
在本教程中，我們將解釋如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件中的圖像周圍放置文字。我們將使用提供的 C# 原始程式碼逐步完成建立表格、新增圖像以及在圖像周圍放置文字的過程。

## 要求

在開始之前，請確保您具備以下條件：

- 安裝了 Aspose.PDF for .NET 函式庫。
- 對 C# 程式設計有基本了解。

## 第 1 步：設定文檔目錄

首先，您需要設定要儲存生成的 PDF 檔案的目錄路徑。代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含您所需目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立文件和頁面

接下來，我們創建一個`Document`對象並使用以下方法向其添加頁面`Pages.Add()`方法。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 3 步：建立表

我們使用以下方法建立一個表`Table`類別並將其新增至頁面的段落集合中。

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## 步驟 4：設定表格列寬和邊距

我們設定表格的列寬並建立一個`MarginInfo`物件設定邊距。

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## 第 5 步：將圖像加入表中

我們創建一個`Image`對象，指定圖片檔案路徑，並設定圖片的固定高度和寬度。然後，我們將圖像新增到表格單元格的段落集合中。

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## 第 6 步：在圖像周圍添加文本

我們創建包含 HTML 格式文字的字串變數並創建`HtmlFragment`目的。然後，我們將 HTML 文字新增到包含圖像的表格單元格中。

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## 第 7 步：新增附加文本

我們創建另一個`HtmlFragment`包含其他 HTML 格式文字的物件並將其新增至單獨的表格儲存格。

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## 步驟 8：儲存 PDF 文檔

最後，我們將PDF文檔儲存到指定的輸出檔案中。

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### 使用 Aspose.PDF for .NET 在圖像周圍放置文字的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//實例化文檔對象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//在 Pdf 中建立頁面
Aspose.Pdf.Page page = doc.Pages.Add();
//實例化一個表對象
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
//將表格新增至所需部分的段落集合中
page.Paragraphs.Add(table1);
//設定表格的列寬
table1.ColumnWidths = "120 270";
//建立 MarginInfo 物件並設定其左、下、右、上邊距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//將預設儲存格填入設定為 MarginInfo 對象
table1.DefaultCellPadding = margin;
//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row1 = table1.Rows.Add();
//建立影像對象
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
//指定影像檔案路徑
logo.File = dataDir + "aspose-logo.jpg";
//指定影像固定高度
logo.FixHeight = 120;
//指定影像固定寬度
logo.FixWidth = 110;
row1.Cells.Add();
//將圖像加入表格單元格的段落集合中
row1.Cells[0].Paragraphs.Add(logo);
//使用包含 html 標籤的文字建立字串變數
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//建立要新增到圖像右側的文字對象
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
//將包含 HTML 文字的文字段落新增至表格單元格
row1.Cells[1].Paragraphs.Add(TitleText);
//將行內容的垂直對齊方式設定為 Top
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
//將第二行的行跨距值設為 2
SecondRow.Cells[0].ColSpan = 2;
//設定第二行垂直對齊方式為Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
//將包含 HTML 文字的文字段落新增至表格單元格
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
//儲存 PDF 文件
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## 結論

在本教學中，您學習如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件中的圖像周圍放置文字。透過遵循逐步指南並執行提供的 C# 程式碼，您可以建立表格、新增圖像以及在 PDF 文件中的圖像周圍放置文字。

### 常見問題解答

#### Q：「在 PDF 文件中的圖像周圍放置文字」教學的目的是什麼？

答：「在 PDF 檔案中的圖像周圍放置文字」教學課程示範如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件中的圖像周圍放置文字。本教學提供逐步指南和 C# 原始程式碼，可協助您建立表格、新增圖像以及在圖像周圍放置文字。

#### Q：為什麼我要在 PDF 文件中的圖像周圍放置文字？

答：在圖像周圍放置文字可以增強 PDF 文件的視覺呈現效果，使其更具吸引力和資訊量。此技術通常用於文件、小冊子、報告和其他您想要以美觀的方式組合圖像和文字的材料。

#### Q：如何設定文檔目錄？

A：設定文檔目錄：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含要儲存產生的 PDF 檔案的目錄路徑。

#### Q：如何建立表格並向其中添加圖像？

答：本教學將引導您完成使用以下命令建立表格的過程：`Table`類別並使用以下命令將圖像添加到表中`Image`班級。在將圖像檔案新增至表格單元格之前，您將指定圖像檔案路徑、高度和寬度。

#### Q：如何在圖像周圍放置文字？

答：要在圖像周圍放置文本，您將使用以下命令創建 HTML 格式的文本：`HtmlFragment`班級。該文字將包含標題和正文。然後，您將將此 HTML 文字新增至與圖像單元格相鄰的表格單元格。

#### Q：我可以自訂文字和圖像的外觀嗎？

答：是的，您可以使用 HTML 標籤和屬性自訂文字和圖像的外觀。例如，您可以設定文字的字體大小、顏色、樣式和對齊方式。此外，您可以調整影像的大小和尺寸。

#### Q：如何儲存PDF文件？

 A：將圖像和文字新增至表格後，您可以使用以下命令儲存PDF文件：`Save`的方法`Document`班級。提供所需的輸出檔案路徑作為參數`Save`方法。

#### Q：本教程的預期輸出是什麼？

答：透過遵循教學課程並執行提供的 C# 程式碼，您將產生一個 PDF 文檔，示範如何在圖像周圍放置文字。輸出文件將包含一個表格，表格周圍有圖像和文字。

#### Q：我可以使用 JPG 以外的其他影像格式嗎？

答：是的，您可以使用 Aspose.PDF 庫支援的不同影像格式，例如 PNG、BMP、GIF 等。創建時`Image`對象，指定所需影像格式的檔案路徑。

#### Q：本教學需要有效的 Aspose 授權嗎？

答：是的，本教學需要有效的 Aspose 許可證才能正常運作。您可以從 Aspose 網站購買完整許可證或取得 30 天的臨時許可證。