---
title: 在 PDF 檔案中填入描邊文本
linktitle: 在 PDF 檔案中填入描邊文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 輕鬆填入 PDF 檔案中的文字並為其新增輪廓。
type: docs
weight: 90
url: /zh-hant/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 檔案中填入和輪廓文字。我們將向您展示如何使用提供的 C# 原始程式碼將填滿和輪廓顏色套用至 PDF 檔案中的文字。

## 第一步：建構環境

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 第 2 步：建立 TextState 對象

第一步是建立一個 TextState 物件來傳遞進階屬性。就是這樣：

```csharp
//建立 TextState 物件以傳遞進階屬性
TextState ts = new TextState();

//設定輪廓顏色
ts.StrokingColor = Color.Gray;

//定義文字渲染模式
ts.RenderingMode = TextRenderingMode.StrokeText;
```

上面的程式碼會建立一個新的 TextState 物件並設定輪廓顏色以及文字的呈現方式。

## 第 3 步：載入 PDF 文檔

現在 TextState 物件已準備就緒，我們可以在要套用文字填滿和輪廓的位置載入 PDF 文件。就是這樣：

```csharp
//載入 PDF 文件作為輸入
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

上面的程式碼使用 Aspose.PDF.Facades 庫中的 PdfFileStamp 類別來載入現有 PDF 文件。

## 步驟 4：為文字新增填滿和描邊

現在 PDF 文件已加載，我們可以向文字添加填充和輪廓。就是這樣：

```csharp
//使用定義的文字和屬性建立圖章（Stamp）
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//綁定 TextState 對象
stamp.BindTextState(ts);

//設定原點X、Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

//將圖章加入文件中
fileStamp.AddStamp(stamp);
```

上面的程式碼建立一個具有指定文字和定義的填滿和描邊屬性的圖章。

## 步驟5：儲存輸出文檔

新增文字圖章後，我們就可以儲存修改後的PDF文件。就是這樣：

```csharp
//儲存修改後的文檔
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

上述程式碼將編輯後的PDF文件儲存到指定目錄。

### 使用 Aspose.PDF for .NET 填入描邊文字的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立 TextState 物件以傳遞進階屬性
TextState ts = new TextState();

//設定描邊顏色
ts.StrokingColor = Color.Gray;

//設定文字渲染模式
ts.RenderingMode = TextRenderingMode.StrokeText;

//載入輸入 PDF 文檔
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//綁定文字狀態
stamp.BindTextState(ts);

//設定X、Y原點
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

//新增圖章
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## 結論

恭喜！您已經學習如何使用 Aspose.PDF for .NET 在 PDF 文件中填入和輪廓文字。現在，您可以應用這些知識來自訂 PDF 文件中的填滿和輪廓顏色。

### PDF 檔案中填入描邊文字的常見問題解答

#### Q：在 PDF 文件中填充和概述文字意味著什麼？何時需要這樣做？

答：在 PDF 文件中填入和輪廓文字涉及將顏色套用至文字字元的內部（填滿）和文字周圍的邊框（輪廓）。這可用於增強文字的視覺外觀、強調或突出顯示 PDF 中的特定內容。

#### Q：提供的C#原始碼如何完成PDF檔案中的文字填入和輪廓顯示？

答：提供的源代碼示範如何創建`TextState`物件來定義進階文字屬性，例如輪廓顏色和渲染模式。然後，它使用 Aspose.PDF.Facades 載入現有 PDF 文檔，建立包含具有指定填滿和描邊屬性的文字的圖章，並將圖章新增至文件中。

####  Q：這樣做的目的是什麼`TextState` object in the code?

答： 的`TextState`物件用於定義進階文字屬性，包括文字輪廓（描邊）的顏色和渲染模式。它允許您自訂文字在描邊和填充方面的顯示方式。

#### Q：我可以對同一文本的不同部分應用不同的填充和輪廓顏色嗎？

 A：是的，您可以修改程式碼來建立不同的`TextState`具有不同填充和輪廓顏色的對象，並使用單獨的方法將它們應用到文字的特定部分`Stamp`對象。

#### Q：我可以將填滿色彩和輪廓顏色套用到 PDF 文件中已有的文字嗎？

答：是的，您可以使用類似的原理將填充和輪廓顏色應用到 PDF 文件中的現有文本，方法是選擇適當的文本對象並將其添加為具有所需顏色的圖章。`TextState`特性。

#### Q：如何調整填滿文字和輪廓文字的不透明度和混合？

答：提供的程式碼可讓您使用以下命令設定圖章的不透明度和混合屬性`Opacity`和`BlendingSpace`屬性，分別。您可以調整這些值以達到所需的視覺效果。

#### Q：如何對同一 PDF 文件中的多個圖章套用不同的填滿和輪廓顏色？

答：可以創建多個`TextState`具有不同填滿和輪廓顏色的對象，然後建立單獨的`Stamp`每組文字的物件具有不同的顏色。使用以下命令將這些圖章新增至同一 PDF 文件中`PdfFileStamp`班級。

#### Q：我可以使用 Arial 以外的字體來顯示輪廓文字和填滿文字嗎？

 A：是的，您可以透過修改字體名稱參數來變更字體`FormattedText`建立圖章時的構造函數。您可以使用系統上可用的任何字體。

#### Q：如何修改輪廓文字和填滿文字的旋轉角度？

答：提供的程式碼可讓您使用設定圖章的旋轉角度`Rotation`財產。您可以調整此屬性來指定文字所需的旋轉角度。

#### Q：如何控制頁面上輪廓文字和填滿文字的位置和大小？

答：您可以使用`SetOrigin`的方法`Stamp`物件設定頁面上圖章位置的 X 和 Y 座標。另外，您也可以調整字體大小`FormattedText`建構函數來控製文字的大小。