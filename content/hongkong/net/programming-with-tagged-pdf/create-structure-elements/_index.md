---
title: 建立結構元素
linktitle: 建立結構元素
second_title: Aspose.PDF for .NET API 參考
description: 在本教學中，您將學習如何使用 Aspose.PDF for .NET 在標記的 PDF 文件中建立結構元素。
type: docs
weight: 60
url: /zh-hant/net/programming-with-tagged-pdf/create-structure-elements/
---
以下 C# 原始程式碼使用 Aspose.PDF for .NET 建立結構元素。請按照以下步驟了解程式碼的工作原理。

## 步驟1：導入必要的庫

```csharp
using Aspose.Pdf;
```

## 第 2 步：定義文檔的目錄

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

請務必指定文件目錄的正確路徑。

## 步驟 3：建立 PDF 文檔

```csharp
Document document = new Document();
```

我們建立一個新的 Document 物件來表示 PDF 文件。

## 第 4 步：取得可與 TaggedPdf 搭配使用的內容

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

我們檢索 PDF 文件的標記內容。這將使我們能夠操縱結構元素。

## 第 5 步：設定文件標題和語言

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

我們設定帶有標籤的 PDF 文件的標題和語言。這提高了文件的可訪問性。

## 第 6 步：建立分組元素

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

我們建立不同的結構元素來將 PDF 文件中的內容分組。

## 步驟 7：建立段落結構元素

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

我們為段落和標題建立區塊級結構元素。上面的範例顯示了 1 級標頭的建立。

## 步驟 8：建立內聯層級結構元素

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

我們為出現在段落或標題內的文字部分建立內聯層級結構元素。

## 第 9 步：建立圖稿結構元素

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

我們為文件中的插圖和數學公式建立結構元素。

## 第10步：儲存標記的PDF文檔

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

我們使用建立的結構元素保存帶有標籤的 PDF 文件。

### 使用 Aspose.PDF for .NET 建立結構元素的範例原始碼 

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
//建立分組元素
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
//建立文字區塊級結構元素
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
//建立文字內嵌結構元素
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
//建立插圖結構元素
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
//方法正在開發中
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
//儲存標記的 PDF 文檔
document.Save(dataDir + "StructureElements.pdf");

```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 在標記的 PDF 文件中建立結構元素。結構元素有助於提高文件的可訪問性並以有意義的方式組織內容。現在，您可以使用這些知識來建立結構化、易於瀏覽的 PDF 文件。

### 常見問題解答

#### Q：使用 Aspose.PDF for .NET 在 PDF 文件中建立結構元素的目的為何？

答：使用 Aspose.PDF for .NET 在 PDF 文件中建立結構元素可以增強文件內容的可存取性和組織性。結構元素提供了分層結構，可改善導航、語義以及與輔助技術的兼容性。

#### Q：所提供的 C# 程式碼如何在 PDF 文件中建立結構元素？

答：程式碼範例示範如何建立各種類型的結構元素，包括分組元素（如部件、節和 div）、區塊級元素（如段落和標題）、內聯級元素（span、quote、note） ）和藝術元素（例如圖形和公式）。這些結構元素有助於組織內容。

####  Q：為什麼使用設定文件的標題和語言很重要`SetTitle` and `SetLanguage` methods?

A：使用設定文件的標題和語言`SetTitle`和`SetLanguage`方法提高了文件的可訪問性和語義。標題提供了文件用途的簡要描述，而語言屬性則增強了特定於語言的呈現和可訪問性。

####  Q：如何將元素分組，例如`PartElement` and `SectElement`, contribute to the structure of the PDF document?

答：將元素分組會在 PDF 文件中建立層次結構，使您能夠邏輯地組織和分組相關內容。這增強了導航並為用戶提供了清晰的結構。

#### Q：什麼是區塊級和內聯級結構元素，它們有何不同？

答：區塊級結構元素表示較大的內容區塊，例如段落和標題，而內嵌級元素表示段落或標題內的文字部分，例如跨距、引號和註釋。它們幫助定義內容的層次結構和關係。

####  Q：藝術品如何構造元素，例如`FigureElement` and `FormulaElement`, contribute to the document?

答：圖稿結構元素可讓您為文件添加插圖、圖形和數學公式。它們提供了一種結構化的方式來包含視覺和數學內容。

#### Q：我可以使用類似的技術來建立其他類型的結構元素，例如清單、表格或註釋嗎？

答：是的，您可以使用類似的技術來建立其他類型的結構元素，例如清單、表格、註釋、參考等。 Aspose.PDF提供了多種結構元素建立方法。

####  Q：如何使用PDF文件儲存有標籤的PDF文件？`Save` method ensure the preservation of structure elements?

答： 的`Save`方法將 PDF 文件與建立的結構元素一起保存，確保保留文件的層次結構和語義結構，以便於存取和導航。

#### Q：結構元素在輔助技術的可存取性和相容性方面為 PDF 文件帶來了哪些好處？

答：結構元素透過為文件提供有意義的結構和語義來增強可訪問性。這使得螢幕閱讀器等輔助技術能夠更有效地向殘障使用者解釋和傳達文件內容。

#### Q：如何在 PDF 文件中進一步自訂和組合不同類型的結構元素？

答：您可以使用Aspose.PDF提供的適當的創建方法來組合和自訂結構元素。嘗試不同的元素及其屬性，以建立結構良好且組織良好的 PDF 文件。