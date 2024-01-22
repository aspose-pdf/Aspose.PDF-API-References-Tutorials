---
title: 邊距或填充
linktitle: 邊距或填充
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在表格中設定邊距或填色。
type: docs
weight: 140
url: /zh-hant/net/programming-with-tables/margins-or-padding/
---
在本教學中，我們將指導您逐步使用 Aspose.PDF for .NET 在表格中設定邊距或填色。我們將提供解釋和程式碼片段來幫助您理解並在 C# 原始程式碼中實現此功能。

## 第 1 步：設定文件和頁面
首先，您需要使用以下程式碼設定文件和頁面：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//透過呼叫其空建構函數來實例化 Document 對象
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 2 步：建立表
接下來，我們將使用 Aspose.Pdf.Table 類別建立一個表格物件：

```csharp
//實例化一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//將表格新增至所需部分的段落集合中
page.Paragraphs.Add(tab1);
```

## 步驟 3：設定列寬和預設儲存格邊框
若要設定表格的列寬和預設儲存格邊框，請使用下列程式碼：

```csharp
//設定表格的列寬
tab1. ColumnWidths = "50 50 50";
//使用 BorderInfo 物件設定預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 步驟 4：設定表格邊框和儲存格填充
若要設定表格邊框和儲存格填充，請建立 MarginInfo 物件並設定其屬性：

```csharp
//建立 MarginInfo 物件並設定其左、下、右、上邊距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

//將預設儲存格填入設定為 MarginInfo 對象
tab1. DefaultCellPadding = margin;

//使用另一個自訂的 BorderInfo 物件設定表格邊框
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## 第 5 步：新增行和儲存格
現在，讓我們在表格中新增行和儲存格。我們將建立一個新行並向其中新增儲存格：

```csharp
//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## 第 6 步：向單元格添加文本
若要將文字新增至儲存格，請建立 TextFragment 物件並將其新增至所需的儲存格：

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## 第 7 步：儲存 PDF
若要儲存 PDF 文檔，請使用以下程式碼：

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
//儲存 PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 的邊距或填入的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//透過呼叫其空建構函數來實例化 Document 對象
Document doc = new Document();
Page page = doc.Pages.Add();
//實例化一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//將表格新增至所需部分的段落集合中
page.Paragraphs.Add(tab1);
//設定表格的列寬
tab1.ColumnWidths = "50 50 50";
//使用 BorderInfo 物件設定預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//使用另一個自訂的 BorderInfo 物件設定表格邊框
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//建立 MarginInfo 物件並設定其左、下、右、上邊距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//將預設儲存格填入設定為 MarginInfo 對象
tab1.DefaultCellPadding = margin;
//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
//Row1.Cells.Add("col3，要放置在單元格內的大文字字串");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
//儲存 PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## 結論
恭喜！您已成功學習如何使用 Aspose.PDF for .NET 在表格中設定邊距或填色。這些知識將幫助您增強文件格式化能力並使您的表格具有視覺吸引力。

### 常見問題解答

#### Q：我可以為表格中的各個儲存格設定不同的邊距或填滿嗎？

答：是的，您可以使用 Aspose.PDF for .NET 為表格中的各個儲存格設定不同的邊距或填滿。在提供的範例中，我們使用以下命令設定整個表格的預設儲存格填充`DefaultCellPadding`財產。若要為特定單元格設定不同的填充，您可以存取`MarginInfo`單獨的每個單元格並修改它們的邊距。

#### Q：如何更改表格的邊框顏色或樣式？

 A：要改變表格的邊框顏色或樣式，可以修改`Color`和`Width`的屬性`BorderInfo`目的。在給定的範例中，我們將邊框顏色設定為黑色，寬度設定為 1F（一點），使用`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`。您可以根據您的要求調整顏色和寬度。

#### Q：是否可以在表格中新增頁首或頁尾？

答：是的，您可以使用 Aspose.PDF for .NET 將頁首或頁尾新增至表格中。頁首和頁尾通常是單獨的行，其中包含附加信息，例如列標籤、表標題或摘要資料。您可以建立其他行，設定不同的樣式，並將它們新增至表格內容的上方或下方。

#### Q：如何調整表格儲存格內的文字對齊方式？

答：若要調整表格儲存格內的文字對齊方式，您可以使用`HorizontalAlignment`和`VerticalAlignment`的屬性`TextFragment`目的。例如，要使文字水平居中對齊，您可以設定`mytext.HorizontalAlignment = HorizontalAlignment.Center;`。同樣，你可以設定`mytext.VerticalAlignment`來控制垂直對齊。

#### Q：我可以在表格單元格中添加圖像而不是文字嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將影像新增至表格儲存格。而不是創建一個`TextFragment`對象，您可以建立一個`Image`對象，加載圖像文件，然後使用以下命令將其添加到所需的單元格`cell.Paragraphs.Add(image);`方法。這允許您將圖像與文字內容一起插入到表格中。