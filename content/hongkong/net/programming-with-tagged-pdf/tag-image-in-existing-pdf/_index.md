---
title: 在現有 PDF 中標記影像
linktitle: 在現有 PDF 中標記影像
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在現有 PDF 中標記影像。向圖像添加標籤的分步指南。
type: docs
weight: 210
url: /zh-hant/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
在本詳細教學中，我們將引導您逐步完成所提供的 C# 原始程式碼，以使用 Aspose.PDF for .NET 在現有 PDF 中標記圖像。請按照以下說明了解如何在 PDF 中的圖像中新增標籤。

## 第一步：建構環境

在開始之前，請確保您已將開發環境配置為使用 Aspose.PDF for .NET。這包括安裝 Aspose.PDF 庫並配置您的專案以引用它。

## 步驟 2：開啟現有 PDF 文檔

在此步驟中，我們將使用 Aspose.PDF 開啟現有的 PDF 文件。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//輸入和輸出檔案路徑
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//開啟文件
Document document = new Document(inFile);
```

我們使用 Aspose.PDF 開啟現有的 PDF 文件。

## 步驟3：取得標記內容和根結構元素

現在我們將取得PDF文件的標記內容以及對應的根結構元素。

```csharp
//取得標記內容和根結構元素
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

我們得到了PDF文件的標記內容以及對應的根結構元素。

## 步驟 4：設定標籤的 PDF 文件的標題

現在讓我們為標籤的 PDF 文件設定標題。

```csharp
//定義標籤的 PDF 文件的標題
taggedContent.SetTitle("Document with images");
```

我們已經為帶有標籤的 PDF 文件設定了標題。

## 第 5 步：為圖像指定替代文字和邊框

現在，對於每個圖像元素，我們將分配替代文字和邊界框。

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     //為圖像指定替代文本
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     //建立並指派邊界框 (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

我們已為 PDF 文件中的每個圖像元素指派了替代文字和邊界框。

## 第 6 步：將 Span 元素移到段落中

現在讓我們將 Span 元素移到段落中。

```csharp
//將 Span 元素移至段落中（在第一個 TD 中找到不正確的 span 和段落）
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//移動段落中的 Span 元素
spanElement.ChangeParentElement(paragraph);
```

我們將 Span 元素移到指定的段落中。

## 步驟7：儲存修改後的PDF文檔

現在我們已經進行了必要的更改，我們將保存修改後的 PDF 文件。

```csharp
//儲存 PDF 文件
document. Save(outFile);
```

我們將修改後的PDF文件保存在指定目錄中。

### 使用 Aspose.PDF for .NET 在現有 PDF 中標記影像的範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//開啟文件
Document document = new Document(inFile);

//取得標記內容和根結構元素
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

//設定帶有標籤的 pdf 文件的標題
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	//設定圖形的替代文本
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	//建立並設定 BBox 屬性
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

//將 Span 元素移至段落中（在第一個 TD 中找到錯誤的 Span 和段落）
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//將 Span 元素移至段落中
spanElement.ChangeParentElement(paragraph);

//儲存文件
document.Save(outFile);

//檢查文件的 PDF/UA 合規性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 在現有 PDF 中標記圖像。現在您可以使用 Aspose.PDF 新增標籤並對 PDF 文件中的影像進行編輯。

### 常見問題解答

#### Q：本教學關於使用 Aspose.PDF for .NET 在現有 PDF 中標記影像的主要目標是什麼？

答：本教學的主要目標是引導您完成使用 Aspose.PDF for .NET 在現有 PDF 文件中標記圖像的過程。本教學提供逐步說明和 C# 原始程式碼範例，幫助您了解如何在圖像中分配替代文字和邊框、移動文件中的元素以及在圖像上新增標籤。

#### Q：學習本教學使用 Aspose.PDF for .NET 在 PDF 中標記影像有哪些先決條件？

答：開始之前，請確保您已設定開發環境以使用 Aspose.PDF for .NET。這涉及安裝 Aspose.PDF 庫並配置您的專案以引用它。

#### Q：如何使用 Aspose.PDF for .NET 開啟現有 PDF 文件並存取其標記內容？

答：本教學提供了 C# 原始碼範例，示範如何使用 Aspose.PDF for .NET 開啟現有 PDF 文件並存取其標記內容以進行進一步操作。

#### Q：為 PDF 文件中的圖像分配替代文字和邊框的目的是什麼？

答：為圖像指派替代文字和邊框可以透過為圖像提供描述性文字並定義其在文件中的佈局和位置來增強可訪問性。這些資訊對於螢幕閱讀器和其他輔助技術至關重要。

#### Q：如何使用 Aspose.PDF for .NET 設定標籤的 PDF 文件的標題？

答：本教學課程包含 C# 原始碼範例，說明如何使用 Aspose.PDF for .NET 設定標記的 PDF 文件的標題。

#### Q：在 PDF 文件中移動元素的過程涉及哪些內容？

答：在 PDF 文件中移動元素涉及更改特定元素的父元素。在本教程中，您將了解如何將 Span 元素移至表中指定的 Paragraph 元素中。

#### Q：新增標籤和編輯影像後，如何儲存修改後的PDF文件？

答：新增標籤、指派替代文字、設定邊界框並對 PDF 文檔進行編輯後，您可以使用提供的 C# 原始碼範例來儲存修改後的 PDF 文檔，方法是使用`Save()`方法。

#### Q：教學中提供的範例原始碼的用途是什麼？

答：範例原始程式碼可作為使用 Aspose.PDF for .NET 實作影像標記和操作的實用參考。您可以使用此程式碼作為起點並對其進行修改以滿足您的特定要求。

#### Q：我可以將這些技術應用於 PDF 文件中的其他類型的元素，而不僅僅是圖像嗎？

答：是的，本教學中示範的技術可以適用於 PDF 文件中的各種類型的元素。您可以應用類似的原則來標記和操作其他元素，例如文字、表格等。

#### Q：如何驗證修改後的 PDF 文件的 PDF/UA 合規性？

答：本教學提供了 C# 原始碼範例，展示如何使用以下命令驗證修改後的 PDF 文件的 PDF/UA 合規性：`Validate()`方法並產生 XML 報告。

#### Q：Aspose.PDF for .NET 還提供哪些其他功能來處理 PDF 文件？

答：Aspose.PDF for .NET 提供了廣泛的處理 PDF 文件的功能，包括文字操作、影像插入、表格建立、表單欄位管理、數位簽章、註解等。請查閱官方文件和資源以進行進一步探索。