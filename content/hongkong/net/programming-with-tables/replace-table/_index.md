---
title: 替換 PDF 文件中的表格
linktitle: 替換 PDF 文件中的表格
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 取代 PDF 文件中的表單。
type: docs
weight: 180
url: /zh-hant/net/programming-with-tables/replace-table/
---
在本教學中，我們將逐步指導您使用 Aspose.PDF for .NET 取代 PDF 文件中的表單。我們將解釋提供的 C# 原始程式碼並向您展示如何實現它。

## 第 1 步：載入現有 PDF 文檔
首先，您需要使用以下程式碼載入現有的 PDF 文件：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入現有的PDF文檔
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## 步驟 2：建立 TableAbsorber 物件來尋找表
接下來，我們將建立一個 TableAbsorber 物件來尋找 PDF 文件中的表格：

```csharp
//建立一個 TableAbsorber 物件來尋找表
TableAbsorber absorber = new TableAbsorber();
```

## 第 3 步：造訪有吸收器的第一頁
我們現在將使用吸收器存取 PDF 文件的第一頁：

```csharp
//訪問帶有吸收器的第一頁
absorb.Visit(pdfDocument.Pages[1]);
```

## 第四步：取得頁面上的第一個表格
為了能夠替換表格，我們將取得頁面的第一個表格：

```csharp
//取得頁面上的第一個表格
AbsorbedTable table = absorb.TableList[0];
```

## 第五步：建立新表
現在我們將建立一個包含所需列和儲存格的新表：

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## 步驟 6：用新表格取代現有表
現在，我們將在文件的第一頁上用新表取代現有表：

```csharp
//將表格替換為新表
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## 步驟 7：儲存文檔
最後，我們儲存修改後的PDF文件：

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### 使用 Aspose.PDF for .NET 取代表格的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入現有 PDF 文檔
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

//建立TableAbsorber物件來尋找表
TableAbsorber absorber = new TableAbsorber();

//訪問帶有吸收器的第一頁
absorber.Visit(pdfDocument.Pages[1]);

//取得頁面上的第一個表格
AbsorbedTable table = absorber.TableList[0];

//建立新表
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

//將桌子更換為新桌子
absorber.Replace(pdfDocument.Pages[1], table, newTable);

//儲存文件
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## 結論
恭喜！現在您已經了解如何使用 Aspose.PDF for .NET 取代 PDF 文件中的表格。本逐步指南向您展示如何載入文件、尋找現有表格、建立新表格以及取代它。現在您可以將這些知識應用到您自己的專案中。

### PDF 文件中替換表格的常見問題解答

#### Q：我可以使用這種方法替換同一 PDF 文件中的多個表格嗎？

答：是的，您可以替換同一 PDF 文件中的多個表格，只需對每個要替換的表格執行相同的流程即可。獲得後`AbsorbedTable`每個表的物件使用`TableAbsorber`，您可以建立對應的新表，然後使用`absorber.Replace()`方法將每個現有表替換為相應的新表。

#### Q：如果新表的列數與原始表不同，會發生什麼情況？

答：如果新表格的列數與原始表格不同，可能會導致修改後的 PDF 文件出現意外行為或佈局問題。必須確保新表的結構（列數及其寬度）與原始表的結構匹配，以實現無縫替換。

#### Q：我可以替換首頁以外的特定頁面上的表格嗎？

答：是的，您可以透過更改頁索引來替換除第一頁之外的特定頁上的表。`pdfDocument.Pages[]`取得時調用方法`AbsorbedTable`目的。例如，要替換第二頁上的表格，您可以使用`pdfDocument.Pages[2]`.

#### Q：我可以自訂新表格的外觀，例如新增背景顏色或邊框嗎？

答：是的，您可以透過設定表的各種屬性來自訂新表的外觀。`Table`及其細胞。例如，您可以設定`BackgroundColor`單元格的屬性添加背景顏色。您也可以設定`DefaultCellBorder`新表格或單一儲存格的屬性以新增邊框。

#### Q：替換表格是否會影響 PDF 文件其餘部分的內容佈局？

答：如果新表格的大小或結構與原始表格顯著不同，則替換表格可能會影響內容佈局。頁面上的其餘內容將重排以適應新表。必須仔細設計新桌子，使其無縫地融入現有佈局，以避免任何佈局問題。