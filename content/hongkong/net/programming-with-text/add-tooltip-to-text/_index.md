---
title: 將工具提示新增至 PDF 檔案中的文本
linktitle: 將工具提示新增至 PDF 檔案中的文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將工具提示新增至 PDF 檔案中的文字。
type: docs
weight: 90
url: /zh-hant/net/programming-with-text/add-tooltip-to-text/
---
本教學將引導您完成使用 Aspose.PDF for .NET 將工具提示新增至 PDF 檔案中的文字的過程。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要為文字新增工具提示的程式碼檔案中，在檔案頂部新增以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 步驟 4：建立帶有文字的範例文檔
創建一個新的`Document`物件並添加帶有文字片段的頁面。在提供的程式碼中，兩個文字片段與各自的工具提示文字一起添加到文件中。

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## 步驟5：開啟文件並找到文字片段
使用以下命令載入建立的文檔`Document`建構函數並使用以下命令尋找需要工具提示的文字片段`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## 第 6 步：在文字片段中新增工具提示
循環遍歷提取的文字片段並在其位置建立不可見的按鈕。將所需的工具提示文字指派給`AlternateName`的財產`ButtonField`。將按鈕欄位新增至文件的表單中。

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## 第 7 步：對帶有長工具提示的其他文字片段重複此操作
對於長工具提示的文字片段，重複步驟 5 和 6。相應地修改搜尋條件和工具提示文字。

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## 步驟8：儲存修改後的文檔
使用以下命令儲存修改後的 PDF 文檔`Save`的方法`Document`目的。

```csharp
document. Save(outputFile);
```

### 使用 Aspose.PDF for .NET 將工具提示新增至文字的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
//建立帶有文字的範例文檔
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
//開啟包含文字的文檔
Document document = new Document(outputFile);
//建立 TextAbsorber 物件以尋找與正規表示式相符的所有短語
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
//接受文件頁面的吸收器
document.Pages.Accept(absorber);
//取得擷取的文字片段
TextFragmentCollection textFragments = absorber.TextFragments;
//循環遍歷片段
foreach (TextFragment fragment in textFragments)
{
	//在文字片段位置建立不可見按鈕
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//AlternateName 值將由檢視器應用程式顯示為工具提示
	field.AlternateName = "Tooltip for text.";
	//將按鈕欄位新增至文件中
	document.Form.Add(field);
}
//接下來是很長的工具提示的樣本
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//設定很長的文本
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
//儲存文件
document.Save(outputFile);
```

## 結論
您已使用 Aspose.PDF for .NET 成功將工具提示新增至 PDF 文件中的文字。現在可以在指定的輸出檔案路徑中找到產生的 PDF 檔案。

## 常見問題解答

#### Q：本教程的重點是什麼？

答：本教學重點在於使用 Aspose.PDF for .NET 函式庫為 PDF 檔案中的文字新增工具提示。提供的 C# 原始程式碼演示了實現此目的所需的步驟。

#### Q：本教學需要導入哪些命名空間？

答：在要為文字新增工具提示的程式碼檔案中，在檔案開頭匯入以下命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Q：如何指定文檔目錄？

 A：在程式碼中找到這一行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何建立帶有文字的範例文件？

答：在步驟 4 中，您將建立一個新的`Document`物件並添加帶有文字片段的頁面。提供的程式碼添加了兩個文字片段以及各自的工具提示文字。

#### Q：如何開啟文件並找到文字片段？

答：在步驟 5 中，您將使用以下命令載入建立的文檔`Document`建構函數並使用以下命令尋找需要工具提示的文字片段`TextFragmentAbsorber`.

#### Q：如何在文字片段中加入工具提示？

答：在步驟 6 中，您將循環遍歷提取的文字片段並在其位置建立不可見的按鈕。工具提示文字被指派給`AlternateName`的財產`ButtonField`，它被添加到文檔的表單中。

#### Q：如何對帶有長工具提示的其他文字片段重複該過程？

答：對於具有長工具提示的文字片段，重複步驟 5 和 6。相應地修改搜尋條件和工具提示文字。

#### Q：如何儲存修改後的文件？

答：在步驟 8 中，您將使用以下命令儲存修改後的 PDF 文件：`Save`的方法`Document`目的。

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經了解如何使用 Aspose.PDF for .NET 為文字新增工具提示來增強 PDF 文件。這可以在讀者與 PDF 內容互動時為他們提供有價值的附加資訊。