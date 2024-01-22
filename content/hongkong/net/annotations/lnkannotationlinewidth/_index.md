---
title: lnk 註解線寬
linktitle: lnk 註解線寬
second_title: Aspose.PDF for .NET API 參考
description: 本文提供了使用 Aspose.PDF for .NET 設定 lnk 註解線寬的逐步指南。
type: docs
weight: 110
url: /zh-hant/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF 是一個功能強大且廣泛使用的工具，可在 .NET 應用程式中處理 PDF 檔案。它提供了用於建立、編輯和操作 PDF 文件的各種功能，包括向頁面添加註釋的功能。在本教學中，我們將說明如何使用 Aspose.PDF for .NET 設定連結註解的線寬。

滿足這些先決條件後，請在 Visual Studio 中建立新的控制台應用程式專案。然後，透過右鍵單擊解決方案資源管理器中的項目，選擇“管理 NuGet 套件”並在 NuGet 套件管理器中搜尋“Aspose.PDF”，新增對 Aspose.PDF for .NET 庫的參考。

若要為 PDF 文件新增 lnk 註釋，請依照下列步驟操作：

## 第 1 步：建立一個新的`Document` object.
```csharp
Document doc = new Document();
```
## 步驟 2：為文件新增頁面。
```csharp
doc.Pages.Add();
```
## 第 3 步：建立一個列表`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
## 第 4 步：建立一個新的`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
## 第 5 步：建立一個新的`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## 步驟 6：將手勢加入墨跡手勢清單。
```csharp
inkList.Add(gesture);
```
## 第 7 步：建立一個新的`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## 步驟8：設定註釋的主題和標題。
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## 步驟9：設定註解的顏色。
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
## 第10步：建立一個新的`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## 第11步：將註解新增至頁面。
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## 第 12 步：將文件儲存到文件中。
```csharp
//儲存輸出檔案
doc.Save(dataDir);


```
### 此範例顯示了 Aspose.PDF for .NET 的 lnk 註解線寬

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
//儲存輸出檔案
doc.Save(dataDir);
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 設定 PDF 文件中連結註解的線寬。 Aspose.PDF for .NET 提供了廣泛的工具和功能來處理 PDF 文檔，包括建立和自訂連結註解的能力。透過遵循逐步指南並使用提供的 C# 原始程式碼，開發人員可以輕鬆地向 PDF 文件添加互動式鏈接，從而增強應用程式的使用者體驗和互動性。 Aspose.PDF for .NET 是一個多功能函式庫，可讓 .NET 開發人員有效率且有效地處理 PDF 檔案。

### 常見問題解答

#### Q：什麼是PDF文件中的連結註解？

答：PDF 文件中的連結註解是一種互動式元素，可讓您建立超連結或操作，將使用者引導至同一文件中的另一個位置、外部網站或不同的 PDF 文件。

#### Q：如何使用 Aspose.PDF for .NET 設定連結註解的線寬？

答：要使用 Aspose.PDF for .NET 設定連結註解的線寬，您可以建立一個`InkAnnotation`物件並指定線寬屬性。

#### Q：可以為 Aspose.PDF for .NET 中的連結註解自訂哪些屬性？

答：您可以在 Aspose.PDF for .NET 中自訂連結註解的各種屬性，例如其位置、大小、顏色、邊框屬性（寬度、樣式、虛線圖案和效果）、主題、標題和可見性。

#### Q：我可以建立包含多個墨跡手勢的連結註解嗎？

答：是的，您可以透過新增多個來建立包含多個墨跡手勢的連結註釋`Point`數組到`InkAnnotation`目的。

#### Q：如何為PDF文件的特定頁面新增連結註解？

 A：要為PDF文件的特定頁面新增連結註釋，需要在建立PDF文件時指定頁碼`InkAnnotation`目的。例如，`new InkAnnotation(doc.Pages[1], ...)`將連結註解新增到第一頁。