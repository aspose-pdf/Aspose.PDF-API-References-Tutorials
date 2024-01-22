---
title: 連結結構元素
linktitle: 連結結構元素
second_title: Aspose.PDF for .NET API 參考
description: 將連結結構元素與 Aspose.PDF for .NET 結合使用的逐步指南。在 PDF 文件中建立超連結。
type: docs
weight: 120
url: /zh-hant/net/programming-with-tagged-pdf/link-structure-elements/
---
在本逐步指南中，我們將向您展示如何將連結結構元素與 Aspose.PDF for .NET 結合使用。 Aspose.PDF 是一個功能強大的程式庫，可讓您以程式設計方式建立和操作 PDF 文件。連結結構元素可讓您為 PDF 文件新增超鏈接，從而允許使用者點擊連結並導航至線上資源。

讓我們深入研究程式碼並了解如何在 Aspose.PDF for .NET 中使用連結結構元素。

## 先決條件

在開始之前，請確保您具備以下條件：

1. 安裝了適用於.NET 的 Aspose.PDF 庫。
2. C# 程式語言的基礎知識。

## 第一步：建構環境

首先，開啟 C# 開發環境並建立一個新專案。請確定您已在專案中新增對 .NET 的 Aspose.PDF 庫的參考。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## 第 2 步：建立文檔

第一步是使用以下命令建立新的 PDF 文檔`Document`班級。

```csharp
//建立 PDF 文件
Document document = new Document();
```

## 第 3 步：處理標記內容

然後我們取得要使用的文檔的標記內容。

```csharp
//取得文件的標記內容
ITaggedContent taggedContent = document.TaggedContent;
```

## 步驟 4：設定文件標題和語言

我們現在可以設定文件標題和語言。

```csharp
//定義文檔標題和語言
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## 第5步：新增連結結構元素

現在讓我們將連結結構元素新增到我們的文件中。我們將創建不同類型的鏈接，包括簡單的文字鏈接、圖像鏈接和多行鏈接。
```csharp
//取得根結構元素（文檔結構元素）
StructureElement rootElement = taggedContent.RootElement;

//添加帶有超連結的段落
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

//添加包含富文本的超連結的段落
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://谷歌.com”）；
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

//新增帶有包含部分格式化文字的超連結的段落
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://谷歌.com”）；
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

//添加帶有多行超連結的段落
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

//添加帶有包含圖像的超連結的段落
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://谷歌.com”）；
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## 步驟 6：儲存標記的 PDF 文檔

最後，我們儲存標記的 PDF 文件。

```csharp
//儲存標記的 PDF 文檔
document. Save(outFile);
```

## 第 7 步：檢查 PDF/UA 合規性

我們也可以使用以下命令檢查文件的 PDF/UA 合規性`Validate`的方法`Document`班級。

```csharp
//檢查 PDF/UA 合規性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### 使用 Aspose.PDF for .NET 的連結結構元素的範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//建立文件並取得標記的 Pdf 內容
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

//設定文件的標題和自然語言
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

//取得根結構元素（文檔結構元素）
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://谷歌.com”）；
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://谷歌.com”）；
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://谷歌.com”）；
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

//儲存標記的 PDF 文檔
document.Save(outFile);

//檢查 PDF/UA 合規性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## 結論

恭喜！您已經學習如何透過 Aspose.PDF for .NET 使用連結結構元素。現在，您可以在 PDF 文件中建立超鏈接，允許使用者導航到線上資源。實驗並探索 Aspose.PDF 的更多功能，以建立互動式且豐富的 PDF 文件。

### 常見問題解答

#### Q：PDF 文件中的連結結構元素是什麼？它們如何增強文件互動性？

答：PDF 文件中的連結結構元素用於建立超鏈接，允許使用者導航到線上資源或文件中的特定位置。這些元素透過提供可點擊的連結來增強互動性，使用戶能夠存取相關內容或外部網站。

#### Q：連結結構元素在 PDF 文件中有何用處？

答：連結結構元素透過使 PDF 文件具有互動性來增強使用者體驗。它們提供對附加資訊、相關內容、外部網站或文件中特定部分的快速訪問，從而改善導航並促進資訊檢索。

#### Q：我可以使用 Aspose.PDF for .NET 中的連結結構元素來建立不同類型的超連結嗎？

答：是的，您可以使用連結結構元素來建立各種類型的超連結。 Aspose.PDF for .NET 可讓您建立純文字、富文本、圖像和多行描述的超鏈接，為您連結到文件中的外部內容或位置提供了多功能性。

#### Q：如何使用 Aspose.PDF for .NET 在 PDF 文件中設定和初始化連結結構元素？

答：要使用連結結構元素，您首先需要使用以下命令建立新的 PDF 文件：`Document`班級。然後，使用以下方法取得標記的內容`TaggedContent`文檔的屬性。從那裡，您可以建立和自訂連結結構元素並將它們新增至根結構元素。

#### Q：如何使用連結結構元素建立簡單的文字超連結？
答：您可以透過建立一個簡單的文字超鏈接`LinkElement`並設定其`Hyperlink`財產給一個`WebHyperlink`以及您想要連結到的 URL。您也可以使用以下命令設定連結的顯示文本`SetText`方法。

#### Q：是否可以使用連結結構元素建立帶有圖像的超連結？

答：是的，您可以使用連結結構元素建立帶有圖像的超連結。你會創建一個`LinkElement`然後附加一個`FigureElement`並帶有圖像。這允許您創建基於圖像的超連結。

#### Q：如何確保帶有超連結的 PDF 文件符合 PDF/UA 標準的可存取性？

答：Aspose.PDF for .NET 能夠使用以下方法驗證您的 PDF 文件是否符合 PDF/UA 標準：`Validate`的方法`Document`班級。這可確保殘障使用者可以存取文件的超連結。

#### Q：連結結構元素的替代描述是什麼，為什麼它們很重要？

答：連結結構元素的替代描述（替代文字）提供超連結的文字描述。這些描述對於可訪問性至關重要，可以讓有視覺障礙的用戶了解連結的用途及其目的地。

#### Q：我可以自訂使用連結結構元素建立的超連結的外觀和行為嗎？

答：雖然連結結構元素主要專注於建立超鏈接，但您可以使用 Aspose.PDF for .NET 提供的其他功能進一步自訂超連結的外觀和行為。這包括指定顏色、樣式和連結操作。

#### Q：連結結構元素如何有助於使 PDF 文件更具互動性和使用者友善性？

答：連結結構元素透過新增可點擊的超連結將靜態 PDF 文件轉換為互動式體驗。這種互動性提高了使用者參與度，實現了相關內容之間的無縫導航，並增強了文件的整體可用性。