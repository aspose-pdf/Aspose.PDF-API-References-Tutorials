---
title: 帶選項的單選按鈕
linktitle: 帶選項的單選按鈕
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 新增單選按鈕，釋放互動式 PDF 的潛力。輕鬆建立引人入勝的表單並改善使用者體驗。
type: docs
weight: 230
url: /zh-hant/net/programming-with-forms/radio-button-with-options/
---
## 介紹

建立互動式 PDF 文件可以顯著增強使用者參與度並簡化資料收集。在您可以合併的各種元素中，單選按鈕作為一種呈現多種選擇選項的用戶友好方法而脫穎而出。使用 Aspose.PDF for .NET，您可以輕鬆地將單選按鈕新增至 PDF 表單中，使用戶可以輕鬆選擇他們的首選項。無論您是在處理調查、反饋表還是應用程序，本指南都將幫助您利用 Aspose.PDF 的強大功能來有效地實現單選按鈕。

## 先決條件

在開始之前，您需要設定一些事項，以確保我們在使用單選按鈕建立 PDF 時順利進行：

1.  Aspose.PDF for .NET：請確定您的專案中已安裝了 Aspose.PDF 庫。如果您還沒有，您可以輕鬆地從[發布頁面](https://releases.aspose.com/pdf/net/).
2. .NET Framework：對 .NET 框架的基本了解將幫助您解決在這個過程中遇到的任何問題。
3. 開發環境：您需要一個合適的 .NET IDE（如 Visual Studio），您可以在其中編寫和測試程式碼。
4. 熟悉 C#：雖然您不需要成為專業人士，但掌握 C# 程式設計肯定會讓這個過程變得更容易、更愉快。
5. PDF 結構的基本知識：了解 PDF 的結構有助於進一步排除故障或自訂表單。

整理好所有這些後，您就可以在 PDF 世界中釋放您的創造力了！

## 導入包

要開始使用 Aspose.PDF 中的單選按鈕，您首先需要將必要的套件匯入到您的 C# 專案中。操作方法如下：

### 打開您的程式碼編輯器

開啟您的開發環境（如 Visual Studio）並建立一個新的 C# 專案（如果您尚未這樣做）。 

### 新增 Aspose.PDF 參考

在解決方案資源管理器中右鍵單擊您的項目，選擇“新增”>“引用”，然後在“組件”部分中尋找 Aspose.PDF。如果您已正確安裝該庫，它應該會出現在清單中。只需勾選它並單擊“確定”即可。

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

現在，您的專案已準備好利用 Aspose 的強大功能！

一切設定完畢後，讓我們一步一步建立一個充滿單選按鈕的 PDF 文件！

## 第 1 步：設定文檔

首先，讓我們建立一個新的 PDF 文件並在其中新增一個頁面。這將是我們繪製單選按鈕選項的畫布。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
```

在此程式碼片段中，我們正在建立一個新的`Document`對象並添加一個`Page`為我們的內容。確保更換`YOUR DOCUMENT DIRECTORY`以及您要儲存 PDF 的路徑。

## 第 2 步：建立佈局表

接下來，我們需要單選按鈕的佈局。使用桌子可以更輕鬆地將它們放置好。

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "120 120 120"; //定義列寬
page.Paragraphs.Add(table);
```

在這裡，我們創建了一個`Table`物件並指定了三列的寬度。這為我們的選項創建了一個整潔的佈局。

## 第 3 步：向表中新增行

現在，我們將在表格和儲存格中新增一行，其中將包含單選按鈕。

```csharp
Row r1 = table.Rows.Add();
Cell c1 = r1.Cells.Add();
Cell c2 = r1.Cells.Add();
Cell c3 = r1.Cells.Add();
```

我們建立一個新行並在該行中建立三個儲存格。每個單元格將包含一個單選按鈕選項。

## 第 4 步：新增單選按鈕字段

這就是有趣的開始 – 讓我們將單選按鈕欄位新增到 PDF 中！

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf.PartialName = "radio";
doc.Form.Add(rf, 1);
```

我們實例化一個`RadioButtonField`，設定其名稱，然後將其新增至文件表單。該欄位將讓用戶做出選擇。

## 第 5 步：配置單選按鈕選項

是時候為單選按鈕建立選項了！我們將新增三個選項供用戶選擇。

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
```

在這裡，我們創建了三個`RadioButtonOptionField`我們每個選擇的實例並為它們分配名稱。利用這些名稱發揮創意可以幫助更好地引導使用者選擇。

## 第 6 步：設定選項尺寸

接下來，讓我們設定單選按鈕選項的大小，使其在視覺上更具吸引力。

```csharp
opt1.Width = 15;
opt1.Height = 15;
opt2.Width = 15;
opt2.Height = 15;
opt3.Width = 15;
opt3.Height = 15;
```

使用此程式碼，我們定義每個單選按鈕的尺寸。如果您需要更大或更小的選項，您可以調整這些值。

## 第 7 步：將選項新增至單選按鈕字段

現在選項已創建，我們需要將它們新增至單選按鈕欄位。

```csharp
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

此程式碼不僅添加了選項，還將它們連結到我們的單選按鈕字段，使用戶能夠選擇其中一個選項。

## 第 8 步：設定選項樣式

為了讓我們的選擇脫穎而出，我們來設計它們的樣式。我們可以新增邊框並設定顏色。

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");
```

重複此樣式`opt2`和`opt3`，相應地調整標題。這確保每個選項看起來專業且有吸引力。

## 第 9 步：為儲存格新增選項

接下來，我們需要將這些單選按鈕放入表格的對應儲存格中。

```csharp
c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

此行將樣式選項新增至我們先前建立的儲存格中，將它們整齊地組織在表格中。

## 第10步：儲存PDF文檔

最後，是時候保存您的工作了！此步驟將我們所做的一切提交到 PDF 文件中。

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
```

使用此程式碼，您的文件將保存在指定的目錄中。現在您可以開啟此 PDF 檔案以查看單選按鈕的運作情況。恭喜您實現了您的第一個互動式 PDF！

## 結論

掌握如何使用 Aspose.PDF for .NET 建立單選按鈕等互動式元素，將為您的 PDF 文件開啟一個全新的可能性領域。透過遵循本指南，您現在應該能夠輕鬆地將單選按鈕合併到您的專案中，從而增強使用者體驗和資料收集流程。無論是簡單的調查還是複雜的表單，建立客製化的互動式 PDF 的能力都觸手可及。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員以程式設計方式建立和操作 PDF 文件。

### 如何安裝 Aspose.PDF for .NET？
您可以從以下位置下載該程式庫[Aspose 發佈頁面](https://releases.aspose.com/pdf/net/)並將其添加到您的項目中。

### 我可以使用其他程式語言在 PDF 中建立單選按鈕嗎？
是的，Aspose.PDF 也可用於 Java 和其他語言以實現類似的功能。

### Aspose.PDF 有免費試用版嗎？
是的，您可以透過下載一個檔案來探索 Aspose.PDF 的功能[免費試用版](https://releases.aspose.com/).

### 我可以在哪裡獲得 Aspose.PDF 支援？
如需支持，您可以訪問[Aspose 支援論壇](https://forum.aspose.com/c/pdf/10)尋求專家和社區成員的協助。