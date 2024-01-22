---
title: 建立多列 PDF
linktitle: 建立多列 PDF
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 建立多列 PDF。
type: docs
weight: 110
url: /zh-hant/net/programming-with-text/create-multi-column-pdf/
---
本教學將引導您完成使用 Aspose.PDF for .NET 建立多列 PDF 的過程。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要建立多列 PDF 的程式碼檔案中，在檔案頂部新增以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 步驟 4：建立一個新的 Document 實例
實例化一個新的`Document`對象，新增以下程式碼行：

```csharp
Document doc = new Document();
```

## 步驟 5：設定頁邊距
使用以下命令指定 PDF 文件的左右邊距信息`PageInfo.Margin`的財產`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## 步驟 6：新增頁面
使用以下命令為文件新增頁面`Add`的方法`Pages`收藏。在提供的程式碼中，新頁面被分配給變數`page`.

```csharp
Page page = doc.Pages.Add();
```

## 步驟7：建立一個Graph物件並新增一條線
創建一個新的`Graph`具有特定尺寸的物件並向其添加一條線。然後，添加`Graph`反對`Paragraphs`頁面的集合。

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## 步驟 8：新增 HTML 格式的標題文本
創建一個`HtmlFragment`物件並將其內容設定為所需的 HTML 文字。然後，將片段加入到`Paragraphs`頁面的集合。

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## 第 9 步：建立一個具有多列的 FloatingBox
創建一個`FloatingBox`物件並設定列數和列間距。然後，將文字片段和一行添加到`Paragraphs`的集合`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## 第10步：儲存PDF文檔
使用以下命令儲存 PDF 文檔`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 建立多列 Pdf 的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//指定 PDF 文件的左距信息
doc.PageInfo.Margin.Left = 40;
//指定 PDF 文件的右距信息
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
//將行加入到節對象的釋義集合中
page.Paragraphs.Add(graph1);
//指定線的座標
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
//使用包含 html 標籤的文字建立字串變數
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
//建立包含 HTML 文字的文字段落
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
//在該部分中新增四列
box.ColumnInfo.ColumnCount = 2;
//設定列之間的間距
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
//建立一個圖形物件來繪製一條線
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
//指定線的座標
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
//將行加入到節物件的段落集合中
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## 結論
您已使用 Aspose.PDF for .NET 成功建立了多列 PDF。現在可以在指定的輸出檔案路徑中找到產生的 PDF 檔案。

### 常見問題解答

#### Q：本教程的重點是什麼？

本教學的重點是引導您完成使用 Aspose.PDF for .NET 程式庫建立多列 PDF 的過程。提供的 C# 原始程式碼演示了實現此目的的必要步驟。

#### Q：在本教程中我應該導入哪些命名空間？

答：在要建立多列 PDF 的程式碼檔案中，在檔案開頭匯入以下命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Q：如何指定文檔目錄？

 A：在程式碼中找到這一行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何建立新的 Document 實例？

答：在步驟 4 中，您將實例化一個新的`Document`使用提供的程式碼的物件。

#### Q：如何設定頁邊距？

答：在步驟 5 中，您將使用`PageInfo.Margin`的財產`Document`指定 PDF 檔案的左右邊距資訊。

#### Q：如何為文件新增頁面？

答：在第 6 步中，您將使用`Add`的方法`Pages`收藏。

#### Q：如何建立 Graph 物件並添加線條？

答：在步驟 7 中，您將建立一個新的`Graph`對象，向其添加一條線，然後添加`Graph`反對`Paragraphs`頁面的集合。

#### Q：如何新增 HTML 格式的標題文字？

答：在步驟 8 中，您將建立一個`HtmlFragment`物件並將其內容設為所需的 HTML 文本，然後將片段新增至`Paragraphs`頁面的集合。

#### Q：如何建立具有多列的 FloatingBox？

答：在步驟 9 中，您將建立一個`FloatingBox`具有多個列和列間距的對象，然後向其中添加文字片段和一行`Paragraphs`的集合`FloatingBox`.

#### Q：如何儲存PDF文件？

答：在步驟 10 中，您將使用以下命令儲存 PDF 文件：`Save`的方法`Document`目的。

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經了解如何使用 Aspose.PDF for .NET 建立多列 PDF 文件。這對於以結構化且有組織的佈局顯示內容非常有用。