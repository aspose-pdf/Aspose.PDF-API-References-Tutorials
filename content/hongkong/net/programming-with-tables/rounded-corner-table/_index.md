---
title: PDF 文件中的圓角表
linktitle: PDF 文件中的圓角表
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中建立圓角表格。
type: docs
weight: 190
url: /zh-hant/net/programming-with-tables/rounded-corner-table/
---
在本教學中，我們將逐步指導您使用 Aspose.PDF for .NET 在 PDF 文件中建立圓角表格。我們將解釋提供的 C# 原始程式碼並向您展示如何實現它。

## 第 1 步：建立表
首先，我們將使用以下程式碼建立表：

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 步驟2：圓角樣式設定
接下來，我們將為表格配置圓角樣式：

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## 步驟 3：表格邊框設置
為了給表格一個圓角邊框，我們需要建立一個 BorderInfo 物件並使用適當的參數來配置它：

```csharp
//建立GraphInfo物件來設定邊框顏色
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

//建立一個空的 BorderInfo 對象
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

//將圓角邊框的半徑設為 15
bInfo.RoundedBorderRadius = 15;

//將邊框資訊應用到表中
tab1.Border = bInfo;
```

### 使用 Aspose.PDF for .NET 的圓角表格的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
//建立一個空白的 BorderInfo 對象
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
//將邊框設為更圓的邊框，其中圓的半徑為 15
bInfo.RoundedBorderRadius = 15;
//將表角樣式設定為圓形。
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
//設定表格邊框訊息
tab1.Border = bInfo;
```

## 結論
恭喜！現在您已經了解如何使用 Aspose.PDF for .NET 在 PDF 文件中建立圓角表格。本逐步指南向您展示如何設定圓角樣式和表格邊框。現在您可以將這些知識應用到您自己的專案中。

### PDF 文件中圓角桌的常見問題解答

#### Q：我可以自訂桌子的圓角半徑嗎？

A：是的，您可以透過修改 的值來自訂表格的圓角半徑。`bInfo.RoundedBorderRadius`提供的 C# 原始碼中的屬性。只需設定所需的半徑值（以磅為單位）即可實現所需的圓角外觀。

#### Q：我可以對表格中的各個單元格應用圓角嗎？

A：不是，圓角樣式是套用於整桌的整體。 Aspose.PDF for .NET 目前不提供表格內各個單元格應用圓角的內建支援。

#### Q：我可以更改圓角邊框的顏色嗎？

 A：是的，可以透過修改圓角邊框的值來改變圓角邊框的顏色`graph.Color`C# 原始碼中的屬性。只需提供所需的顏色，例如`Aspose.Pdf.Color.Red`或任何其他有效的顏色表示。

#### Q：是否可以對同一 PDF 文件中的不同表格套用不同的角落樣式（例如方形和圓形）？

答：是的，可以對同一 PDF 文件中的不同表格套用不同的角落樣式。您可以建立多個表格並根據您的要求單獨配置其角樣式。

#### Q：我可以調整圓角邊框的粗細嗎？

 A：是的，您可以透過修改圓角邊框的粗細來調整`BorderInfo`C# 原始碼中物件的屬性。例如，您可以設定`bInfo.Width`屬性來調整邊框的粗細。