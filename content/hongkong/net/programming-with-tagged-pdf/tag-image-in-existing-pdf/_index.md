---
title: 在現有 PDF 中標記影像
linktitle: 在現有 PDF 中標記影像
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在現有 PDF 中標記影像。透過 PDF/UA 合規性增強可訪問性的逐步指南。
type: docs
weight: 210
url: /zh-hant/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## 介紹

在本教學中，我們將引導您了解如何使用 Aspose.PDF for .NET 在現有 PDF 中標記圖像。在本指南結束時，您將能夠設定圖像的替代文字、調整佈局屬性並確保您的 PDF 符合輔助功能標準。

## 先決條件

在我們深入討論之前，讓我們回顧一下開始之前需要做的事情：

-  Aspose.PDF for .NET：請確定您已下載並安裝最新版本的 Aspose.PDF for .NET。[在此下載](https://releases.aspose.com/pdf/net/).
- .NET Framework：確保您已設定 Visual Studio 等 .NET 開發環境。
- 對 PDF 結構的基本了解：熟悉 PDF 結構元素，例如段落、跨度、表格和圖像。
- 有效許可證：您可以購買許可證[這裡](https://purchase.aspose.com/buy)或使用臨時的[這裡](https://purchase.aspose.com/temporary-license/).

## 導入包

要開始編碼，您需要從 Aspose.PDF for .NET 匯入基本的命名空間。這些將使您能夠存取操作 PDF 文件所需的類別和方法。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

現在我們已經做好了準備，讓我們將標記圖像的過程分解為多個步驟。

## 第 1 步：載入現有 PDF 文檔

第一步是載入您要使用的 PDF 文件。這可以是任何帶有您想要標記的圖像的 PDF 文件。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//開啟文件
Document document = new Document(inFile);
```

- 代替`"YOUR DOCUMENT DIRECTORY"`與文件的實際路徑。
- 這`Document`類別允許您載入現有的 PDF。您將修改此 PDF 以標記圖像。

## 第 2 步：存取標記內容和根結構元素

打開 PDF 後，下一步是存取標記的內容並識別根結構元素。這一點至關重要，因為它允許您瀏覽 PDF 中的元素並進行修改。

```csharp
//取得標記內容和根結構元素
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent`提供對 PDF 中結構化元素的存取。
- 這`RootElement`是最頂層的結構元素，您可以從中遍歷到其他元素，例如段落、表格和圖像。

## 步驟 3：設定標籤的 PDF 文件的標題

在標籤的 PDF 文件中新增標題可確保您的文件被正確標記，這有助於輔助功能和 PDF/UA 合規性。

```csharp
//設定帶有標籤的 PDF 文件的標題
taggedContent.SetTitle("Document with images");
```

- 為標籤的 PDF 設定標題可以增強螢幕閱讀器和輔助技術的可存取性並提高文件清晰度。

## 第 4 步：尋找並標記圖像

現在，讓我們找到圖像元素（稱為`FigureElement`在Aspose.PDF中），為其設定替代文本，並配置其佈局屬性。

```csharp
//循環遍歷所有Figure 元素（圖像）並設定替代文字和佈局屬性
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    //設定圖形的替代文本
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    //建立並設定BBox屬性（邊界框）
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    //設定圖窗的佈局屬性
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

- 這段程式碼循環遍歷所有`FigureElement`根結構中的對象，代表圖像。
- 它設定可訪問性的替代文字（螢幕閱讀器將使用它來描述圖像）。
- 邊界框 (`BBox`指定影像佈局的座標，確保其在文件中正確顯示。

## 步驟 5：修改表格中的 Span 元素

在某些情況下，您可能需要修改表中的跨度元素。在這裡，我們將示範如何找到`SpanElement`並將其移動到一個段落。

```csharp
//尋找表格、跨度和段落元素
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//將 span 元素移動到段落中
spanElement.ChangeParentElement(paragraph);
```

- 在這裡，我們找到`TableElement`, `SpanElement`， 和`ParagraphElement`在 PDF 內。
- 使用`ChangeParentElement`方法中，我們將跨度移動到段落中以確保正確的標記和結構。

## 步驟 6：儲存文件並驗證 PDF/UA 合規性

完成所有變更後，最後一步是儲存更新的 PDF 並檢查其是否符合 PDF/UA 標準。

```csharp
//儲存更新的 PDF 文檔
document.Save(outFile);

//驗證 PDF/UA 合規性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

- 這`Validate`方法根據 PDF/UA 標準檢查 PDF 文件並記錄結果。
- 確保合規性有助於提高可訪問性並滿足文件發布的監管要求。

## 結論

在本教學中，我們向您展示如何使用 Aspose.PDF for .NET 在現有 PDF 中標記圖像。透過設定替代文字、調整佈局屬性以及驗證文件是否符合 PDF/UA 合規性，您可以確保您的 PDF 易於存取並符合現代標準。 Aspose.PDF 讓使用結構化元素變得容易，讓您可以控製文件的佈局和可訪問性。

## 常見問題解答

### Aspose.PDF for .NET 的用途是什麼？
Aspose.PDF for .NET 是一個功能強大的程式庫，用於在 .NET 環境中以程式設計方式建立、編輯和操作 PDF 文件。

### 如何確保 PDF/UA 合規性？
你可以使用Aspose.PDF的`Validate`對文件進行修改後檢查 PDF/UA 合規性的方法。

### PDF 中的替代文字是什麼？
替代文字是添加到 PDF 圖像中的描述，以提高可訪問性，特別是對於依賴螢幕閱讀器的用戶。

### 我可以使用 Aspose.PDF 操作 PDF 中的表格和跨度嗎？
是的，Aspose.PDF 可讓您操作 PDF 文件中的表格、跨度和其他結構化元素。

### 哪裡可以下載 Aspose.PDF for .NET？
您可以下載最新版本的 Aspose.PDF for .NET[這裡](https://releases.aspose.com/pdf/net/).