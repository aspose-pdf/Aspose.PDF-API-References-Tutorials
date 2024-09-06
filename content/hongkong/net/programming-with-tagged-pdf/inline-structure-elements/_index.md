---
title: 內聯結構元素
linktitle: 內聯結構元素
second_title: Aspose.PDF for .NET API 參考
description: 透過 Aspose.PDF for .NET 使用線上結構元素的逐步指南。使用標題和段落組織您的 PDF。
type: docs
weight: 110
url: /zh-hant/net/programming-with-tagged-pdf/inline-structure-elements/
---
在本逐步指南中，我們將向您展示如何在 Aspose.PDF for .NET 中使用內嵌結構元素。 Aspose.PDF 是一個功能強大的程式庫，可讓您以程式設計方式操作 PDF 文件。內嵌結構元素可讓您使用不同層級和段落的標題在 PDF 文件中建立層次結構。

讓我們深入研究程式碼並了解如何在 Aspose.PDF for .NET 中使用內聯結構元素。

## 先決條件

在開始之前，請確保您具備以下條件：

1. 安裝了適用於.NET 的 Aspose.PDF 庫。
2. C# 程式語言的基礎知識。

## 第一步：建構環境

首先，開啟 C# 開發環境並建立一個新專案。請確定您已在專案中新增對 .NET 的 Aspose.PDF 庫的參考。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## 第5步：線上新增結構元素

現在我們將向文件添加內聯結構元素，例如不同層級的標題和段落。

```csharp
//取得根結構元素
StructureElement rootElement = taggedContent.RootElement;

//新增不同等級的標題
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

//在每個標題中新增內容
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

//新增一段
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

//為段落添加內容
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

在這裡，我們創建內聯結構元素，例如不同層級的標題和段落，並在其中添加內容。

## 步驟 6：儲存標記的 PDF 文檔

最後，我們儲存標記的 PDF 文件。

```csharp
//儲存標記的 PDF 文檔
document.Save(dataDir + "InlineStructureElements.pdf");
```

### 使用 Aspose.PDF for .NET 的內嵌結構元素的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立 PDF 文件
Document document = new Document();

//取得與 TaggedPdf 一起使用的內容
ITaggedContent taggedContent = document.TaggedContent;

//設定文檔網的標題和語言
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

//取得根結構元素
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

//儲存標記的 PDF 文檔
document.Save(dataDir + "InlineStructureElements.pdf");

```

## 結論

恭喜！您已經了解如何透過 Aspose.PDF for .NET 使用內聯結構元素。現在，您可以使用不同層級和段落的標題在 PDF 文件中建立層次結構。探索 Aspose.PDF 的更多功能以發現其全部潛力。

### 常見問題解答

#### Q：PDF 文件中的內聯結構元素是什麼？

答：PDF 文件中的內聯結構元素（例如不同層級的標題和段落）用於建立分層結構，以結構化方式組織和呈現內容。這些元素可讓您在文件中建立清晰的層次結構和資訊流。

#### Q：內嵌結構元素如何增強 PDF 文件的可讀性和組織性？

答：內聯結構元素，特別是標題和段落，透過提供邏輯結構來幫助提高 PDF 文件的可讀性和組織性。標題表示不同的重要性等級並幫助讀者瀏覽內容，而段落則將相關資訊分組在一起。

#### Q：Aspose.PDF for .NET 如何促進內聯結構元素的使用？

答：Aspose.PDF for .NET 提供了類別和方法來建立和操作內聯結構元素，例如標題和段落。這些元素可以進行自訂、分層組織並豐富內容，以改善文件的視覺呈現和可訪問性。

####  Q：這樣做的目的是什麼`taggedContent` object in relation to inline structure elements?

答： 的`taggedContent`對象，從獲得`TaggedContent`的財產`Document`，允許您使用結構化元素，包括內聯結構元素。它使您能夠建立、自訂和組織文件中的標題和段落。

#### Q：內聯結構元素如何幫助創建清晰的文件層次結構？

答：內聯結構元素（例如不同層級的標題）有助於在文件中建立清晰且定義明確的層次結構。讀者可以快速識別主主題、副主題和相關內容，使文件更易於瀏覽和理解。

#### Q：我可以使用 Aspose.PDF for .NET 自訂內聯結構元素的外觀和格式嗎？

答：是的，您可以自訂內聯結構元素的外觀和格式。您可以設定字體樣式、大小、顏色、對齊方式、縮排和間距等屬性，以實現標題和段落所需的視覺呈現。

#### Q：如何使用 Aspose.PDF for .NET 中的內聯結構元素建立不同層級的標題並將其新增至 PDF 文件？

答：您可以使用以下命令建立不同層級的標題`CreateHeaderElement`方法，然後將它們附加到根結構元素。隨後，您可以使用以下命令為每個標題元素添加內容`CreateSpanElement`建立文字跨度的方法。

#### Q：我可以使用內嵌結構元素在 PDF 文件中建立清單、項目符號或其他類型的內容組織嗎？

答：雖然內聯結構元素本身主要用於標題和段落，但您可以將它們與Aspose.PDF for .NET 提供的其他功能結合使用，以建立清單、項目符號點、表格和其他類型的內容組織，以實現全面的內容組織。

#### Q：內聯結構元素如何有助於文件的可存取性？

答：內聯結構元素在增強文件可存取性方面發揮著至關重要的作用。結構正確的標題和段落提供了清晰的文件層次結構，有助於螢幕閱讀器和其他輔助技術準確地向殘障使用者解釋和傳達內容。

#### Q：我可以探索內嵌結構元素的更高級用途，例如建立互動式元素或嵌入多媒體嗎？

答：當然！雖然本教學重點介紹建立標題和段落，但 Aspose.PDF for .NET 提供了建立互動式元素、嵌入多媒體、新增超連結等進階功能。檢查庫的文檔和範例以深入研究這些高級功能。