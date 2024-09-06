---
title: 頁首頁腳中的可替換符號
linktitle: 頁首頁腳中的可替換符號
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首和頁尾中使用可替換符號。
type: docs
weight: 320
url: /zh-hant/net/programming-with-text/replaceable-symbols-in-header-footer/
---
在本教學中，我們將說明如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件的頁首和頁尾中使用可替換符號。我們將逐步完成建立 PDF、設定邊距、使用可替換符號新增頁首和頁尾以及使用提供的 C# 原始碼儲存 PDF 的過程。

## 先決條件

在開始之前，請確保您具備以下條件：

- 安裝了 Aspose.PDF for .NET 函式庫。
- 對 C# 程式設計有基本了解。

## 第 1 步：設定文檔目錄

首先，您需要設定要儲存生成的 PDF 檔案的目錄路徑。代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含您所需目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立 PDF 文件和頁面

接下來，我們建立一個新的 PDF 文件並使用以下命令向其中新增頁面`Document`類和`Page`來自 Aspose.PDF 庫的類別。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 3 步：設定邊距

我們使用以下命令設定頁面的邊距`MarginInfo`班級。根據您的要求調整邊距值。

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## 步驟 4：新增可替換符號的標題

我們創建一個`HeaderFooter`頁面物件並新增`TextFragment`帶有可替換的符號。

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
//如果需要，設定文字屬性
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

//添加更多 TextFragments 或根據需要進行自訂
```

## 第 5 步：新增帶有可替換符號的頁腳

同樣，我們創建一個`HeaderFooter`頁面頁腳物件並新增`TextFragment`帶有可替換符號的物件。

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

//添加更多 TextFragments 或根據需要進行自訂

hfFoot.Paragraphs.Add(tab2);
```

## 步驟 6：儲存 PDF 文檔

最後，我們將PDF文檔儲存到指定的輸出檔案中。

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 在頁首頁腳中取代符號的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//將 marginInfo 執行個體指派給 sec1.PageInfo 的 Margin 屬性
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
//實例化一個文字段落，該段落將儲存要顯示為標題的內容
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
//為該部分建立 HeaderFooter 對象
HeaderFooter hfFoot = new HeaderFooter();
//將 HeaderFooter 物件設定為奇數頁腳和偶數頁腳
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
//新增包含目前頁碼佔總頁數的文字段落
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
//實例化一個表對象
Table tab2 = new Table();
//將表格新增至所需部分的段落集合中
hfFoot.Paragraphs.Add(tab2);
//設定表格的列寬
tab2.ColumnWidths = "165 172 165";
//在表格中建立行，然後在行中建立儲存格
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
//設定文字的垂直對齊方式為居中對齊
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java 是Aspose 提供的每個Java 元件的編譯。它是在#$NL" + "每日基礎上編譯的，以確保它包含每個元件的最新版本#$NL " + "使用 Aspose.Total for Java 開發人員可以建立廣泛的應用程式 #$NL #$NL #$NP" + "Aspose.Total for Java 是每個 Java 元件的編譯。提供。 for Java 是Aspose 提供的每個Java 元件的編譯，它每天都會編譯，以確保它包含最多的內容。 。
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
//將表格新增至所需部分的段落集合中
page.Paragraphs.Add(table);
//使用 BorderInfo 物件設定預設儲存格邊框
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
//使用另一個自訂的 BorderInfo 物件設定表格邊框
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//在表格中建立行，然後在行中建立儲存格
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## 結論

在本教學中，您學習如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件的頁首和頁尾中使用可替換符號。透過遵循逐步指南並執行提供的 C# 程式碼，您可以建立 PDF、設定邊距、新增帶有可替換符號的頁首和頁腳，以及儲存 PDF。

### 常見問題解答

#### Q：「頁眉頁腳中的可替換符號」教學的目的為何？

答：「頁首頁腳中的可替換符號」教學課程旨在引導您完成使用 .NET 的 Aspose.PDF 庫為 PDF 文件的頁首和頁尾新增可替換符號的過程。可替換符號可讓您在產生 PDF 時以實際值動態取代特定佔位符。

#### Q：PDF 頁首和頁尾上下文中的可替換符號有哪些？

答：可替換符號是可以插入 PDF 文件頁首和頁尾中的佔位符。這些符號可作為可在執行時間填入的值的動態佔位符，例如頁碼、日期和自訂資訊。

#### Q：為什麼我要在 PDF 頁首和頁尾中使用可替換符號？

答：當您想要在 PDF 文件中包含動態資訊（例如頁碼、日期或產生文件時可能會變更的其他可變資料）時，頁首和頁尾中的可替換符號非常有用。

#### Q：如何設定PDF頁面的邊距？

答：您可以使用以下指令設定 PDF 頁面的邊距`MarginInfo`類別並將其分配給`Margin`的財產`PageInfo`頁面的。根據需要調整邊距值。

#### Q：如何在頁首和頁尾新增可替換符號？

答：您可以透過建立一個來新增可替換符號`HeaderFooter`頁面的頁首和頁尾物件。然後，您可以添加`TextFragment`具有所需文字（包括可替換符號）的對象`Paragraphs`的集合`HeaderFooter`目的。

#### Q：我可以自訂可替換符號的外觀嗎？

答：是的，您可以透過修改可替換符號的屬性來自訂可替換符號的外觀。`TextFragment`包含符號的物件。您可以設定字體、字體大小、顏色、對齊方式和行距等屬性。

#### Q：我可以使用什麼類型的可替換符號？

答：您可以使用多種可替換的符號，例如：

- `$p`：當前頁碼。
- `$P`：總頁數。
- `$d`：當前日期。
- `$t`：當前時間。
- 您定義的自訂佔位符。

#### Q：我可以在可替換符號周圍包含其他文字和格式嗎？

答：是的，您可以在可替換符號周圍包含其他文字和格式`TextFragment`對象。這允許您建立包含動態和靜態內容的更複雜的頁首和頁尾。

#### Q：如何儲存產生的PDF文件？

 A：要儲存產生的PDF文檔，您可以使用`Save`的方法`Document`班級。提供所需的輸出檔案路徑和名稱作為參數。

#### Q：本教學需要有效的 Aspose 授權嗎？

答：是的，需要有效的 Aspose 許可證才能成功執行本教程中的程式碼。您可以從 Aspose 網站取得完整許可證或 30 天臨時許可證。