---
title: 在 PDF 檔案中設定標註屬性
linktitle: 在 PDF 檔案中設定標註屬性
second_title: Aspose.PDF for .NET API 參考
description: 在此詳細的逐步教學中，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定標註屬性。
type: docs
weight: 130
url: /zh-hant/net/annotations/setcalloutproperty/
---
## 介紹

建立專業且具有視覺吸引力的 PDF 文件通常需要添加註釋以引起對特定內容的注意。其中一個註釋是標註，它就像您在漫畫中看到的那些對話氣泡。它們有助於澄清或強調 PDF 中的文字。 Aspose.PDF for .NET 讓在文件中新增此類註解變得異常簡單，在本教學中，我們將逐步介紹如何使用此功能強大的程式庫在 PDF 檔案中設定標註屬性。無論您是經驗豐富的開發人員還是新手，在本指南結束時，您都會清楚地了解如何使用 PDF 文件中的標註。

## 先決條件

在深入研究程式碼之前，讓我們先介紹一下入門所需的基礎知識。

1.  Aspose.PDF for .NET：請確定您已安裝 Aspose.PDF for .NET 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/pdf/net/).
2. IDE：開發環境，例如 Visual Studio。
3. .NET Framework：確保您的電腦上安裝了 .NET。
4. 臨時許可證：如果您想不受限制地嘗試 Aspose.PDF 的全部功能，請取得[臨時執照](https://purchase.aspose.com/temporary-license/).

## 導入包

在開始編寫程式碼之前，您需要匯入必要的套件，以便您可以使用 PDF 文件和註釋。

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

這些匯入將為您提供操作 PDF 文件和建立標註（如標註）所需的所有類別和方法。

## 步驟1：初始化PDF文檔

我們旅程的第一步是初始化一個新的 PDF 文檔，我們將在其中添加標註註釋。將此視為設定空白畫布，您可以在其中開始新增元素。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//初始化一個新的PDF文檔
Document doc = new Document();
```
在這裡，我們正在創建一個新的`Document`對象，它將作為我們的 PDF 文件。這`dataDir`變數設定為完成後您要儲存 PDF 檔案的目錄。

## 步驟 2：為文件新增頁面

PDF 文件可以有多個頁面，在這一步驟中，我們將在文件中新增一個新頁面。此頁面將放置我們的標註註釋。

```csharp
//新增頁面
Page page = doc.Pages.Add();
```
這`Pages.Add()`方法用於將新頁面新增至`doc`目的。新頁面儲存在`page`變量，我們稍後在添加註釋時將使用該變量。

## 第 3 步：定義預設外觀

註釋（如標註）具有可自訂的視覺外觀。在此步驟中，我們將定義標註中文字的外觀。

```csharp
//定義註釋的預設外觀
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
我們創建一個`DefaultAppearance`定義文字顏色和字體大小的物件。此處，文字將為紅色，字體大小設定為 10。

## 第 4 步：建立自由文字註釋

現在是時候創建實際的註釋了。自由文字註釋允許我們添加具有特定文字和樣式的標註。

```csharp
//建立帶有標註的 FreeTextAnnotation
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
我們創建一個`FreeTextAnnotation`具有特定座標的對象，定義其在頁面上的位置。這`Intent`設定為`FreeTextCallout`，表示這是一個標註註釋。這`EndingStyle`設定為`OpenArrow`，這意味著標註線將以空心箭頭結束。

## 第 5 步：定義標註線點

標註註釋有一條線指向感興趣的區域。在這裡，我們將定義組成這條線的點。

```csharp
//定義標註線的點
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
這`Callout`屬性是一個數組`Point`對象，每個對象代表頁面上的一個座標。這些點定義標註線的路徑，賦予其經典的對話框外觀。

## 第 6 步：將註釋新增至頁面

建立並配置註釋後，下一步是將其新增至頁面。

```csharp
//新增註解到頁面
page.Annotations.Add(fta);
```
這`Annotations.Add()`方法用於將註釋放置在我們之前建立的頁面上。此步驟有效地在 PDF 頁面上「繪製」標註。

## 步驟7：設定富文本內容

標註註釋可以包含富文本，從而允許氣泡內包含格式化內容。讓我們添加一些範例文字。

```csharp
//設定註釋的富文本
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">這是一個例子</span></p></body>";
```
這`RichText`屬性是用 HTML 內容設定的。這允許在標註中進行詳細的格式化，例如指定字體大小、顏色和樣式。

## 步驟 8：儲存 PDF 文檔

最後，設定完所有內容後，我們需要儲存文件。此步驟完成帶有標註註釋的 PDF 的建立。

```csharp
//儲存文件
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
這`Save()`方法將文件儲存到指定目錄，檔案名稱為「SetCalloutProperty.pdf」。這一步結束了我們的 PDF 建立過程。

## 結論

現在你就擁有了！您剛剛使用 Aspose.PDF for .NET 建立了一個帶有標註註釋的 PDF 文件。此註釋對於突出顯示或解釋文件的特定部分非常有用。 Aspose.PDF 提供了強大的 API，讓 PDF 操作變得簡單又靈活。無論您是新增註解、轉換文件還是處理複雜的 PDF 任務，Aspose.PDF 都能滿足您的需求。

## 常見問題解答

### 我可以進一步自訂標註的外觀嗎？

絕對地！您可以自訂各個方面，例如線條顏色、粗細以及文字的字體系列和樣式。

### 是否可以在單一頁面上新增多個標註？

是的，您可以透過對每個註釋重複這些步驟來根據需要添加任意數量的標註。

### 如何更改標註的位置？

只需修改其中的座標即可`Rectangle`和`Callout`屬性來重新定位註釋。

### 我可以使用 Aspose.PDF 新增其他類型的註解嗎？

是的，Aspose.PDF 支援各種註解類型，包括反白、圖章和文件附件。

### 富文本內容是否僅限於 HTML？

這`RichText`屬性支援 HTML 的子集，可讓您包含樣式文字和基本格式。