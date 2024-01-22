---
title: 將結構元素加入元素中
linktitle: 將結構元素加入元素中
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將結構元素新增至 PDF 文件中的元素的逐步指南。
type: docs
weight: 20
url: /zh-hant/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
在本教程中，我們將為您提供有關如何使用 Aspose.PDF for .NET 將結構元素新增至 PDF 文件中的元素的逐步指南。 Aspose.PDF 是一個功能強大的程式庫，可讓您以程式設計方式建立、操作和轉換 PDF 文件。使用Aspose.PDF的標記內容結構功能，您可以在PDF文件中建立層次結構。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1. 隨 .NET Framework 安裝的 Visual Studio。
2. 適用於 .NET 的 Aspose.PDF 庫。

## 第 1 步：項目設置

首先，在 Visual Studio 中建立一個新專案並新增對 Aspose.PDF for .NET 程式庫的參考。您可以從Aspose官方網站下載該程式庫並將其安裝到您的電腦上。

## 第 2 步：導入必要的命名空間

在您的 C# 程式碼檔案中，匯入存取 Aspose.PDF 提供的類別和方法所需的命名空間：

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 步驟 3：建立 PDF 文件並定義結構化元素

使用以下程式碼建立 PDF 文件並定義結構化元素：

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

此程式碼會建立一個空的 PDF 文件並添加結構化元素，例如段落和跨度。每個結構元素都是使用 Aspose.PDF 提供的方法建立的。

## 步驟 4：儲存 PDF 文檔

使用以下程式碼儲存PDF文件：

```csharp
document. Save(outFile);
```

此程式碼將帶有結構化元素的 PDF 文件儲存到指定文件中。

### 使用 Aspose.PDF for .NET 將結構元素新增至元素中的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
//建立文件並取得標記的 Pdf 內容
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
//設定文件的標題和自然語言
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
//取得根結構元素（文檔結構元素）
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
//儲存標記的 PDF 文檔
document.Save(outFile);
//檢查 PDF/UA 合規性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

在本教學中，您學習如何使用 Aspose.PDF for .NET 將結構元素新增至 PDF 文件中的元素。使用Aspose.PDF的標記內容結構功能，您可以在PDF文件中建立層次結構，這使得管理和瀏覽內容變得更加容易。

### 常見問題解答

#### Q：使用 Aspose.PDF for .NET 將結構元素新增至 PDF 文件中的元素的目的為何？

答：使用 Aspose.PDF for .NET 將結構元素新增至 PDF 文件中的元素可讓您在文件內容中建立層次結構。這種層次結構增強了內容的組織和導航，使管理和存取特定元素變得更加容易。

#### Q：Aspose.PDF 庫如何協助在 PDF 文件中新增結構元素？

答：Aspose.PDF for .NET 是一個功能強大的函式庫，提供以程式設計方式建立、操作和轉換 PDF 文件的功能。在本教學中，利用庫的標記內容結構功能來建立結構元素並將其附加到 PDF 文件的內容。

#### Q：使用 Aspose.PDF for .NET 將結構元素新增至 PDF 文件的先決條件是什麼？

答：開始之前，請確保您已安裝了具有 .NET 框架的 Visual Studio，並在專案中引用了適用於 .NET 的 Aspose.PDF 程式庫。

#### Q：提供的 C# 程式碼如何建立結構元素並將其附加到 PDF 文件的內容？

答：程式碼示範如何建立 PDF 文件、定義根結構元素以及向其附加各種結構化元素（例如段落和跨度）。每個結構化元素都是使用 Aspose.PDF 提供的方法建立的，讓您可以建立層次結構。

#### Q：我可以自訂附加到 PDF 文件的結構元素類型嗎？

答：是的，您可以透過探索 Aspose.PDF 庫提供的不同方法來自訂結構元素的類型。該程式碼展示了段落和跨度作為範例，但您可以根據需要建立和附加其他類型的結構化元素。

#### Q：如何定義新增的結構元素之間的層次關係？

答：結構元素之間的層次關係由將它們附加到其父元素的順序定義。在程式碼中，父子關係是透過使用`AppendChild`方法。

#### Q：在 PDF 文件中建立層次結構有什麼好處？

答：在 PDF 文件中建立層次結構可以增強其可訪問性、導航和組織。它允許輔助技術更好地解釋和傳達文件的內容，使其對殘疾人士來說更加用戶友好。

#### Q：新增結構元素後如何驗證 PDF/UA 合規性？

答：本教學中提供的程式碼示範如何使用以下方法驗證 PDF/UA 合規性：`Validate`方法。透過根據 PDF/UA 標準驗證文檔，您可以確保新增的結構元素符合輔助功能指南。

#### Q：我可以使用此方法為現有 PDF 文件添加結構元素嗎？

答：是的，您可以修改提供的方法以將結構元素新增至現有 PDF 文件中。您可以使用 Aspose.PDF 載入現有文檔，然後按照類似的步驟附加結構元素，而不是建立新文檔。