---
title: 連結結構元素
linktitle: 連結結構元素
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中建立連結結構元素。新增可存取連結、圖像和合規性驗證的逐步指南。
type: docs
weight: 120
url: /zh-hant/net/programming-with-tagged-pdf/link-structure-elements/
---
## 介紹

在 PDF 中建立和管理連結結構元素對於需要可存取性和流暢導航的文件至關重要。在本教學中，我們將引導您了解如何使用 Aspose.PDF for .NET 執行此操作。如果您對 Aspose.PDF 或一般 PDF 操作不熟悉，請不要擔心。我將詳細解釋每個步驟，以便您可以輕鬆地進行操作！

## 先決條件  

在我們深入編碼之前，讓我們先解決一些問題。這些是保證流暢的開發體驗的基本要求。

1.  Aspose.PDF for .NET：您可以下載最新版本[這裡](https://releases.aspose.com/pdf/net/).
2. .NET 開發環境：無論是 Visual Studio 或任何與 .NET 相容的 IDE，都已安裝並準備就緒。
3.  Aspose 授權：您可以使用 Aspose.PDF 的免費試用版[這裡](https://releases.aspose.com/)或獲得一個[臨時執照](https://purchase.aspose.com/temporary-license/).
4. C# 基礎知識：我們將使用一些 C# 程式碼，因此了解基礎知識將使事情變得更加容易。

## 導入包

在編寫連結結構元素的程式碼之前，您需要導入一些套件。首先在專案中引用必要的 Aspose.PDF 庫：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些匯入使我們能夠處理 PDF 文件、新增標籤和管理結構元素。

我們現在將建立一個具有不同類型連結結構的 PDF 文檔，並將分解每個步驟，以幫助您徹底理解該過程。

## 步驟1：初始化文檔  

讓我們先建立一個新的 PDF 文件並設定標記內容以方便存取。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//建立新的 PDF 文檔
Document document = new Document(); 

//檢索 TaggedContent 介面
ITaggedContent taggedContent = document.TaggedContent;
```
  
在這裡，我們正在初始化`Document`對象，它代表我們的 PDF 文件。我們也檢索`TaggedContent`介面，允許我們添加結構元素，例如段落、連結和圖像。

## 第 2 步：設定標題和語言  

每個 PDF 都應該有標題和語言設置，特別是如果您的目標是遵守 PDF/UA 標準。

```csharp
//設定文檔標題和語言
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
此步驟可確保您的 PDF 具有有意義的標題並將語言設定為英文 (`en-US`）。這對於可訪問性至關重要，並確保螢幕閱讀器或其他輔助技術可以正確解釋您的文件。

## 第 3 步：建立並附加段落  

在此步驟中，我們將新增段落來儲存連結元素。

```csharp
//建立根元素
StructureElement rootElement = taggedContent.RootElement;

//建立一個段落並將其新增至根元素
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
我們創建一個根結構元素，它本質上是所有其他元素的頂級容器。然後我們創建一個段落（`p1`) 並將其附加到根元素。

## 第 4 步：新增簡單鏈接  

現在讓我們新增一個指向 Google 的基本超連結。

```csharp
//建立一個連結元素並將其添加到段落中
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

//設定超連結和連結文本
link1.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
在此步驟中，我們創建了一個連結元素，將其超連結設定為“http://google.com”，並為該連結提供了文字（“Google”）。我們還添加了替代說明以確保可訪問性。

## 第 5 步：添加帶有 Span 的鏈接  

我們還可以建立具有不同文字跨度的連結。

```csharp
//創建另一個段落
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

//使用 span 元素創建鏈接
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://谷歌.com”）；

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
在這裡，我們使用 span 元素將部分文字包含在連結內，從而允許我們自訂連結某些部分的顯示方式。

## 第 6 步：多行鏈接  

如果您的連結文字太長怎麼辦？不用擔心，您可以將其分成多行。

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
在本例中，我們透過簡單地設定一個長文字值來建立多行鏈接，文字將自動換行。

## 第 7 步：將圖像新增至鏈接  

最後，您也可以在連結內添加圖像。

```csharp
//建立一個新的段落和連結元素
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://谷歌.com”）；

//將圖像添加到鏈接
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
此步驟示範如何增強影像的連結。在本例中，我們在連結內新增了一個 Google 圖示。我們還透過為圖像設定替代文字來確保可訪問性。

## 第 8 步：驗證 PDF 的合規性  

如果您的目標是實現 PDF/UA 合規性（一種輔助使用標準），那麼驗證您的文件是一個很好的做法。

```csharp
//儲存 PDF 文件
document.Save(outFile);

//驗證文件的 PDF/UA 合規性
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
我們保存了文件並根據 PDF/UA 標準對其進行了驗證，這確保了 PDF 滿足輔助功能要求。

## 結論  

在本教學中，我們介紹如何使用 Aspose.PDF for .NET 建立結構化 PDF 文件。從添加基本的超鏈接到更複雜的結構（如跨度、多行鏈接，甚至圖像），本指南為操作 PDF 中的鏈接元素奠定了堅實的基礎。憑藉 PDF/UA 合規性的額外優勢，您現在可以製作可存取和可導航的 PDF。

## 常見問題解答

### 我可以添加更複雜的結構，例如連結內的表格嗎？  
不，連結主要用於文字和圖像，但您可以在附近嵌入複雜的元素。

### PDF/UA 驗證是否是強制性的？  
並不總是如此，但如果您擔心可訪問性，強烈建議您這樣做。

### 如果圖片檔案路徑不正確怎麼辦？  
該文件不會顯示圖像，並且在渲染過程中可能會引發錯誤。

### 我可以設定連結內文字的樣式嗎？  
是的，您可以使用 span 元素來套用文字樣式。

### 是否可以建立內部文件連結？  
絕對地！您可以連結到同一文件中的特定部分。